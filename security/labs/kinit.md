# Output of kinit

```
[root@ip-172-32-4-188 ~]# kinit cloudera-scm -V
```

```
Using default cache: /tmp/krb5cc_0
Using principal: cloudera-scm@COMPUTE.INTERNAL
Password for cloudera-scm@COMPUTE.INTERNAL:
Authenticated to Kerberos v5
```

# Output of klist

```
[root@ip-172-32-4-188 ~]# klist -e
```

```
Ticket cache: FILE:/tmp/krb5cc_0
Default principal: cloudera-scm@COMPUTE.INTERNAL

Valid starting     Expires            Service principal
10/18/17 20:03:05  10/19/17 20:03:05  krbtgt/COMPUTE.INTERNAL@COMPUTE.INTERNAL
        renew until 10/25/17 20:03:05, Etype (skey, tkt): arcfour-hmac, arcfour-hmac
```