# Yarn calcs

I have 4 m4.xlarge AWS instances, so I set the spreadsheet according to this.
This is only a test cluster for SEBC, thereby the spreadsheet don't get exact values, because the hosts don't have sufficient resources. 
For example it say I need 2 cores for OS and 1 core for CM Agent. It will work with only 1 core in this case.
Of course, if we want a real production Big Data cluster, we need more powerful machines.

## workload factor

The workload factor can get a minimum value for the number of map and reduce tasks. 
If in our cluster need much resource for the jobs, we should calculate min number of tasks with 4 workload value, otherwise with 1.