---
title: Members API Reference

language_tabs:
  - shell : cURL
  - java
  - csharp
  - ruby

toc_footers:
 - <a href='mailto:KurumsalCozumlerGelistirmeBolumu@borsaistanbul.com'>Contact for Support</a>
---

# Introduction

Member Service is an entity service. Technically it'll allow you to interact with any member information in the company. There can be only one state of any member and the most recent state of the member is what you will be interacting.



# Interacting with Members



## Getting All Members

> To get all the members, use this code:

```shell
# make sure curl is installed in your system
curl "http://<api-endpoint>/members"
```

```java
// Use https://github.com/JoeJErnst/http-client as an example to create something simple like below
// Otherwise check out Google HTTP Client or Apache HTTP Client for more complex scenarios

Response response = new Request("http://<api-endpoint>/members").getResource();
String allMembersInJson = response.getBody();
```

```csharp
var client = new WebClient();
string allMembersInJson = client.DownloadString("http://<api-endpoint>/members");
```

```ruby
# make sure you have rest-client gem installed in your system
allMembersInJson = RestClient.get "http://<api-endpoint>/members"
```

This endpoint retrieves all the members in the company.

> The above command returns JSON structured like this:

```json
{
  "href": "/members",
  "members": [
    {
      "href": "/members/id/92",
      "id": 92
    },
    {
      "href": "/members/id/93",
      "id": 93
    }
  ]
}
```

### HTTP Request

`GET /members`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
expand | none | If set to **items**, the result will also include member details.




## Getting Members by Code

> To get a specific member by code, use this code:

```shell
# make sure curl is installed in your system
curl "http://<api-endpoint>/members/code/<code>"
```

```java
// Use https://github.com/JoeJErnst/http-client as an example to create something simple like below
// Otherwise check out Google HTTP Client or Apache HTTP Client for more complex scenarios

Response response = new Request("http://<api-endpoint>/members/code/<code>").getResource();
String memberInJson = response.getBody();
```

```csharp
var client = new WebClient();
string memberInJson = client.DownloadString("http://<api-endpoint>/members/code/<code>");
```

```ruby
# make sure you have rest-client gem installed in your system
memberInJson = RestClient.get "http://<api-endpoint>/members/code/<code>"
```

This endpoint retrieves the member details for the given code.

> The above command returns JSON structured like this:

```json
{
  "href": "/members/id/289",
  "id": 289,
  "code": "ADY",
  "title": "ANADOLU YATIRIM MENKUL KIYMETLER A.Ş."
}
```

### HTTP Request

`GET /members/code/<code>`

### Query Parameters

Not defined.




## Getting Members by Id

> To get a specific member by id, use this code:

```shell
# make sure curl is installed in your system
curl "http://<api-endpoint>/members/id/<id>"
```

```java
// Use https://github.com/JoeJErnst/http-client as an example to create something simple like below
// Otherwise check out Google HTTP Client or Apache HTTP Client for more complex scenarios

Response response = new Request("http://<api-endpoint>/members/id/<id>").getResource();
String memberInJson = response.getBody();
```

```csharp
var client = new WebClient();
string memberInJson = client.DownloadString("http://<api-endpoint>/members/id/<id>");
```

```ruby
# make sure you have rest-client gem installed in your system
memberInJson = RestClient.get "http://<api-endpoint>/members/id/<id>"
```

This endpoint retrieves the member details for the given id.

> The above command returns JSON structured like this:

```json
{
  "href": "/members/id/289",
  "id": 289,
  "code": "ADY",
  "title": "ANADOLU YATIRIM MENKUL KIYMETLER A.Ş."
}
```

### HTTP Request

`GET /members/id/<id>`

### Query Parameters

Not defined.





# Health Check



## Ping (Heartbeat)

> To ping the service, use this code:

```shell
# make sure curl is installed in your system
curl "http://<api-endpoint>/ping"
```

```java
// Use https://github.com/JoeJErnst/http-client as an example to create something simple like below
// Otherwise check out Google HTTP Client or Apache HTTP Client for more complex scenarios

Response response = new Request("http://<api-endpoint>/ping").getResource();
String pong = response.getBody();
```

```csharp
var client = new WebClient();
string pong = client.DownloadString("http://<api-endpoint>/ping");
```

```ruby
# make sure you have rest-client gem installed in your system
pong = RestClient.get "http://<api-endpoint>/ping"
```

This is a heart beat or ping/pong endpoint for this service. It'll give you very quick response if the service is alive.

> The above command returns JSON structured like this:

```json
{
  "ping": "OK"
}
```

### HTTP Request

`GET /ping`

### Query Parameters

Not defined.




## Status

> To get the status of the service, use this code:

```shell
# make sure curl is installed in your system
curl "http://<api-endpoint>/status"
```

```java
// Use https://github.com/JoeJErnst/http-client as an example to create something simple like below
// Otherwise check out Google HTTP Client or Apache HTTP Client for more complex scenarios

Response response = new Request("http://<api-endpoint>/status").getResource();
String pong = response.getBody();
```

```csharp
var client = new WebClient();
string pong = client.DownloadString("http://<api-endpoint>/status");
```

```ruby
# make sure you have rest-client gem installed in your system
pong = RestClient.get "http://<api-endpoint>/status"
```

With this endpoint, you can get very technical details about the service. 

> The above command returns JSON structured like this:

```json
{
  "status": "OK",
  "version": "1.0.5857",
  "dependencies": {
    "status": "OK",
    "services": []
  },
  "infra": {
    "status": "OK",
    "cpuUsage": "1.07%",
    "memoryUsage": "33.06%",
    "totalMemory": "3,958.21 MB",
    "jvm": {
      "vm_name": "Java HotSpot(TM) 64-Bit Server VM",
      "vm_version": "23.21-b01",
      "memory": {
        "totalInit": "85.03 MB",
        "totalUsed": "58.61 MB",
        "totalMax": "1,010 MB",
        "totalCommitted": "110.69 MB",
        "heapInit": "61.85 MB",
        "heapUsed": "19.28 MB",
        "heapMax": "880 MB",
        "heapCommitted": "35.31 MB",
        "heap_usage": "0%",
        "non_heap_usage": "0%"
      },
      "buffers": {
        "direct_count": 10,
        "direct_memory_used": "0.16 MB",
        "direct_capacity": "0.16 MB",
        "mapped_count": 0,
        "mapped_memory_used": "0 MB",
        "mapped_capacity": "0 MB"
      },
      "daemon_thread_count": "8",
      "thread_count": "25",
      "current_time": "1,384,154,306,251 ms",
      "uptime": "9,177,714.89 ms",
      "thread_state_counts": {
        "terminated": 0,
        "waiting": 5,
        "timed_waiting": 15,
        "runnable": 5,
        "blocked": 0,
        "new": 0
      },
      "garbage_collectors": [
        {
          "name": "PS Scavenge",
          "count": 1853,
          "time": 9955
        },
        {
          "name": "PS MarkSweep",
          "count": 1,
          "time": 234
        }
      ]
    },
    "disks": {
      "status": "OK",
      "diskList": [
        {
          "mountPoint": "/",
          "usage": "65.45%",
          "totalSpace": "15.53 GB"
        }
      ]
    },
    "os": "Linux"
  },
  "databases": {
    "status": "OK",
    "dbList": [
      {
        "name": "Oracle",
        "status": "OK"
      }
    ]
  }
}
```

### HTTP Request

`GET /status`

<aside class="warning">If you are seeing **WARNING** or **CRITICAL** as the service status, you should contact the service administrators immediately.</aside>

### Query Parameters

Not defined.





## Service Logs

> To get the logs of the service, use this code:

```shell
# make sure curl is installed in your system
curl "http://<api-endpoint>/logs"
```

```java
// Use https://github.com/JoeJErnst/http-client as an example to create something simple like below
// Otherwise check out Google HTTP Client or Apache HTTP Client for more complex scenarios

Response response = new Request("http://<api-endpoint>/logs").getResource();
String pong = response.getBody();
```

```csharp
var client = new WebClient();
string pong = client.DownloadString("http://<api-endpoint>/logs");
```

```ruby
# make sure you have rest-client gem installed in your system
pong = RestClient.get "http://<api-endpoint>/logs"
```

With this endpoint, you can get all the service logs.

> The above command returns log statements like below:

```
INFO  [2013-11-11 12:13:56,080] com.sun.jersey.api.container.filter.LoggingFilter: 19 * Server in-bound request
INFO  [2013-11-11 12:13:55,927] com.sun.jersey.api.container.filter.LoggingFilter: 18 * Server out-bound response
INFO  [2013-11-11 12:13:55,756] com.sun.jersey.api.container.filter.LoggingFilter: 18 * Server in-bound request
ERROR [2013-11-11 12:13:22,616] com.borsaistanbul.entity.employee.exception.RuntimeExceptionMapper: Status Code : 404
java.lang.Thread.run(Thread.java:722)
org.eclipse.jetty.util.thread.QueuedThreadPool$3.run(QueuedThreadPool.java:543)
org.eclipse.jetty.util.thread.QueuedThreadPool.runJob(QueuedThreadPool.java:608)
org.eclipse.jetty.server.nio.BlockingChannelConnector$BlockingChannelEndPoint.run(BlockingChannelConnector.java:298)
org.eclipse.jetty.server.BlockingHttpConnection.handle(BlockingHttpConnection.java:72)
org.eclipse.jetty.http.HttpParser.parseAvailable(HttpParser.java:235)
org.eclipse.jetty.http.HttpParser.parseNext(HttpParser.java:640)
org.eclipse.jetty.server.AbstractHttpConnection$RequestHandler.headerComplete(AbstractHttpConnection.java:1004)
org.eclipse.jetty.server.AbstractHttpConnection.headerComplete(AbstractHttpConnection.java:942)
org.eclipse.jetty.server.BlockingHttpConnection.handleRequest(BlockingHttpConnection.java:53)
org.eclipse.jetty.server.AbstractHttpConnection.handleRequest(AbstractHttpConnection.java:489)
org.eclipse.jetty.server.Server.handle(Server.java:368)
org.eclipse.jetty.server.handler.HandlerWrapper.handle(HandlerWrapper.java:116)
org.eclipse.jetty.server.handler.HandlerCollection.handle(HandlerCollection.java:154)
com.yammer.dropwizard.jetty.BiDiGzipHandler.handle(BiDiGzipHandler.java:123)
org.eclipse.jetty.server.handler.GzipHandler.handle(GzipHandler.java:264)
com.yammer.metrics.jetty.InstrumentedHandler.handle(InstrumentedHandler.java:200)INFO  [2013-11-11 09:21:46,326] com.sun.jersey.api.container.filter.LoggingFilter: 17 * Server out-bound response
INFO  [2013-11-11 09:21:46,300] com.borsaistanbul.capability.controllers.LoginAttemptsController: Create login attempt: 
```

### HTTP Request

`GET /logs`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
filter | none | If set, the result will filtered by the given keyword
reverse | true | If set to **false**, the result will be shown in ascending order
lines | 3000 | If set, the result will contain only the given number of lines




## Access Logs

> To get the access logs of the service, use this code:

```shell
# make sure curl is installed in your system
curl "http://<api-endpoint>/logs/access"
```

```java
// Use https://github.com/JoeJErnst/http-client as an example to create something simple like below
// Otherwise check out Google HTTP Client or Apache HTTP Client for more complex scenarios

Response response = new Request("http://<api-endpoint>/logs/access").getResource();
String pong = response.getBody();
```

```csharp
var client = new WebClient();
string pong = client.DownloadString("http://<api-endpoint>/logs/access");
```

```ruby
# make sure you have rest-client gem installed in your system
pong = RestClient.get "http://<api-endpoint>/logs/access"
```

With this endpoint, you can get the access logs for the service.

> The above command returns log statements like below:

```
10.40.8.54 - - [11/Nov/2013:12:27:04 +0000] "GET /logs HTTP/1.1" 200 835 22 22
10.40.8.54 - - [11/Nov/2013:12:13:22 +0000] "GET /favicon.ico HTTP/1.1" 404 49 7 7
10.40.8.54 - - [11/Nov/2013:12:13:22 +0000] "GET /status HTTP/1.1" 200 599 147 147
10.12.1.12 - - [11/Nov/2013:09:21:46 +0000] "GET /employees/member/id/335 HTTP/1.1" 200 3618 138 138
```

### HTTP Request

`GET /logs/access`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
filter | none | If set, the result will filtered by the given keyword
lines | 3000 | If set, the result will contain only the given number of lines




## GC Logs

> To get the garbage collection logs for the service, use this code:

```shell
# make sure curl is installed in your system
curl "http://<api-endpoint>/logs/gc"
```

```java
// Use https://github.com/JoeJErnst/http-client as an example to create something simple like below
// Otherwise check out Google HTTP Client or Apache HTTP Client for more complex scenarios

Response response = new Request("http://<api-endpoint>/logs/gc").getResource();
String pong = response.getBody();
```

```csharp
var client = new WebClient();
string pong = client.DownloadString("http://<api-endpoint>/logs/gc");
```

```ruby
# make sure you have rest-client gem installed in your system
pong = RestClient.get "http://<api-endpoint>/logs/gc"
```

With this endpoint, you can get the gc logs for the service.

> The above command returns all the garbage collection activities in log statements like below:

```
2013-11-11T13:30:03.013+0200: 934731.082: [GC [PSYoungGen: 3466K->160K(3648K)] 44812K->41513K(45888K), 0.0036800 secs] [Times: user=0.01 sys=0.00, real=0.00 secs] 
2013-11-11T11:08:22.917+0200: 926230.986: [GC [PSYoungGen: 3157K->256K(3648K)] 44230K->41337K(45888K), 0.0041510 secs] [Times: user=0.01 sys=0.01, real=0.00 secs] 
2013-11-11T03:37:03.365+0200: 899151.435: [GC [PSYoungGen: 3392K->480K(3648K)] 43729K->40825K(45888K), 0.0024630 secs] [Times: user=0.01 sys=0.00, real=0.00 secs] 
2013-11-11T01:29:42.410+0200: 891510.480: [GC [PSYoungGen: 3348K->384K(3648K)] 43478K->40521K(45888K), 0.0018990 secs] [Times: user=0.01 sys=0.00, real=0.00 secs] 
2013-11-10T15:41:41.903+0200: 856229.973: [GC [PSYoungGen: 3348K->384K(3648K)] 42517K->39561K(45888K), 0.0031510 secs] [Times: user=0.00 sys=0.00, real=0.01 secs] 
2013-11-10T13:54:21.803+0200: 849789.873: [GC [PSYoungGen: 3157K->256K(3648K)] 42151K->39257K(45888K), 0.0049520 secs] [Times: user=0.01 sys=0.00, real=0.01 secs] 
2013-11-10T05:29:11.355+0200: 819479.424: [GC [PSYoungGen: 3350K->384K(3648K)] 41512K->38553K(45888K), 0.0017050 secs] [Times: user=0.00 sys=0.00, real=0.00 secs] 
2013-11-10T01:24:11.151+0200: 804779.220: [GC [PSYoungGen: 3348K->384K(3648K)] 41110K->38153K(45888K), 0.0053070 secs] [Times: user=0.01 sys=0.00, real=0.01 secs] 
2013-11-09T13:23:06.681+0200: 761514.751: [GC [PSYoungGen: 3707K->288K(3904K)] 40348K->36937K(46144K), 0.0029440 secs] [Times: user=0.00 sys=0.00, real=0.00 secs] 
2013-11-09T02:00:36.053+0200: 720564.122: [GC [PSYoungGen: 3750K->192K(3840K)] 39231K->35681K(46080K), 0.0051510 secs] [Times: user=0.01 sys=0.00, real=0.01 secs] 
2013-11-08T01:19:44.793+0200: 631712.862: [GC [PSYoungGen: 4151K->384K(4544K)] 37437K->33678K(46784K), 0.0029000 secs] [Times: user=0.00 sys=0.00, real=0.00 secs] 
2013-11-07T20:44:24.528+0200: 615192.597: [GC [PSYoungGen: 4322K->224K(4544K)] 37257K->33166K(46784K), 0.0096660 secs] [Times: user=0.02 sys=0.00, real=0.01 secs] 
2013-11-07T07:43:43.846+0200: 568351.915: [GC [PSYoungGen: 5028K->224K(5248K)] 34178K->29382K(47488K), 0.0015130 secs] [Times: user=0.01 sys=0.00, real=0.00 secs]
```

### HTTP Request

`GET /logs/gc`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
filter | none | If set, the result will filtered by the given keyword
lines | 3000 | If set, the result will contain only the given number of lines
