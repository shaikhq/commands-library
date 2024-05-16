# How to Set up TCP/IP Communication in a Db2 Instance?

In this document, I am sharing the steps of enabling tcpip protocol for connecting to a Db2 instance. Once the tcpip protocol is enabled in Db2, you can connect to your Db2 instance via a tcpip port. 

1. Set the communication protocol of your Db2 instance to TCP/IP:
```shell
db2set db2comm=tcpip
```

`db2set`: this command sets the registry variables of a Db2 instance. In this case, you're using it to set the value of the registry variable `db2comm`, the variable that enables the protocol for connecting to a Db2 instance. 

2. Print the TCP/IP port number currently configured at the Db2 instance. For first time setup of TCP/IP at a Db2 instance, this value will be empty. 

```shell
db2 get dbm cfg | grep -i svcename
```
![alt text](image.png)

`db2 get dbm cfg` commands retrieves current Db2 configuration parameters. `grep -i svcename` is filtering the list of 
parameters to only `svcename`, the TPC/IP port number. 

3. Now, set the TCP/IP port number to 50000
```shell
db2 update dbm cfg using SVCENAME 50000
```

4. Restart Db2 instance:
```shell
db2stop force
db2start
```

Now, your application can connect to Db2 via TPC/IP on port 50000 :). 
