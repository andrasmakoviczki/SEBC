# YARNtest.sh

```
#!/bin/sh
# Confirm the path values given below correspond to your installation

MR=/opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce
HADOOP=/opt/cloudera/parcels/CDH/bin
HADOOPUSER=andrasmakoviczki

# Mark start of the loop
echo Testing loop started on `date`

# Mapper containers
for i in 1 2 4
do
   # Reducer containers
   for j in 1 2
   do
      # Container memory
      for k in 512 1024 2048
      do
         # Set mapper JVM heap
         MAP_MB=`echo "($k*0.8)/1" | bc`

         # Set reducer JVM heap
         RED_MB=`echo "($k*0.8)/1" | bc`

       echo -e "--------------------------"
       echo -e "MAPPER\t\t = $i"
       echo -e "REDUCER\t\t = $j"
       echo -e "CONTAINER MEMORY = $k"
       echo -e "--------------------------"

       echo -e "--------------------------"
       echo -e "TERAGEN TIME"
       echo -e "--------------------------"

       time ${HADOOP}/hadoop jar ${MR}/hadoop-examples.jar teragen \
                     -Dmapreduce.job.maps=$i \
                     -Dmapreduce.map.memory.mb=$k \
                     -Dmapreduce.map.java.opts.max.heap=$MAP_MB \
                     51200000 /user/${HADOOPUSER}/results/tg-10GB-${i}-${j}-${k} 1>tera_${i}_${j}_${k}.out 2>tera_${i}_${j}_${k}.err

       echo -e "--------------------------"
       echo -e "TERASORT TIME"
       echo -e "--------------------------"

       time ${HADOOP}/hadoop jar $MR/hadoop-examples.jar terasort \
                     -Dmapreduce.job.maps=$i \
                     -Dmapreduce.job.reduces=$j \
                     -Dmapreduce.map.memory.mb=$k \
                     -Dmapreduce.map.java.opts.max.heap=$MAP_MB \
                     -Dmapreduce.reduce.memory.mb=$k \
                     -Dmapreduce.reduce.java.opts.max.heap=$RED_MB \
                     /user/${HADOOPUSER}/results/tg-10GB-${i}-${j}-${k}  \
                     /user/${HADOOPUSER}/results/ts-10GB-${i}-${j}-${k} 1>>tera_${i}_${j}_${k}.out 2>>tera_${i}_${j}_${k}.err

        echo -e "\n"
        echo -e "--------------------------"
        echo -e "CLEAN"
        echo -e "--------------------------"

        $HADOOP/hadoop fs -rm -r -skipTrash /user/${HADOOPUSER}/results/tg-10GB-${i}-${j}-${k}
        $HADOOP/hadoop fs -rm -r -skipTrash /user/${HADOOPUSER}/results/ts-10GB-${i}-${j}-${k}

        echo -e "\n"
        echo -e "--------------------------"
        echo -e "END"
        echo -e "--------------------------"

      done
   done
done

echo Testing loop ended on `date`
```