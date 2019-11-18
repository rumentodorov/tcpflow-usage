# How to track calls to external services with tcpflow

It is a common case when we have Microservice A calling Microservice B. To do so we need a way to check what calls do we do to external services. If we have service mesh and a monitoring it will help, but there ase simple situations when I need to run a service on my pc and inspect the http class to a specific external service. This can be done with tpcflow.

```sh
$ sudo tcpflow -p -c -i <interface> port <port>
```
Where :
-p: don't use promiscuous mode
-c: console print only (don't create files)
-i: network interface on which to listen

Example:
```sh
$ sudo tcpflow -p -c -i eth0 port 80
```
Now call www.google.com on your browser