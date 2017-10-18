# Kinit to Server

```
[root@ip-172-32-11-139 ~]# kinit -V cloudera-scm
Using default cache: /tmp/krb5cc_0
Using principal: cloudera-scm@COMPUTE.INTERNAL
Password for cloudera-scm@COMPUTE.INTERNAL:
Authenticated to Kerberos v5
```

# Klist
```
[root@ip-172-32-11-139 ~]# klist -e
Ticket cache: FILE:/tmp/krb5cc_0
Default principal: cloudera-scm@COMPUTE.INTERNAL

Valid starting     Expires            Service principal
10/18/17 20:51:53  10/19/17 20:51:53  krbtgt/COMPUTE.INTERNAL@COMPUTE.INTERNAL
        renew until 10/25/17 20:51:53, Etype (skey, tkt): arcfour-hmac, arcfour-hmac

```