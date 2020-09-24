# 14-Web-Development-Homework-README.md## Unit 14 Homework: Web Development

#### HTTP Requests and Responses

Answer the following questions about the HTTP request and response process.

1. What type of architecture does the HTTP request and response process occur in?
  *HTTP is based on the client-server architecture model and a stateless request/response protocol that operates by exchanging messages across a reliable TCP/IP connection.

2. What parts make up an `HTTP request`?
   *The GET method requests a representation of the specified resource. Requests using GET should only retrieve data.

3. What is the optional part of an HTTP request?
Anything below `headers`, which is `Request body` is optional.

4. What three parts make up an HTTP response?
The status line, some headers, and an optional body.

5. Which number class of status codes represent errors?
400 CODES

6. What are the two most common request methods that a security professional will come across?
GET and POST

7. Which type of HTTP request method is used for sending data?
POST

8. Which part of an `HTTP request` contains the data being sent to the server?
POST
9. In which part of an HTTP response would the browser receive the web code to generate and style a web page?
Cookie
#### Using cURL

Answer the following questions about `curl`:

10. What are the advantages of using curl over the browser?
The advantages of using curl are sometimes, the tools you can use to send and receive http requests are limited, so when working through a container that has no user interface, you'll need a command-line tool to send and receive http requests. And it is also a quick way to test HTTP requests in a way that can be automated.

11. Which curl option is used to change the request method?
-- request: set the request type

12. Which curl option is used to set request headers?
-H: Sets a request header

13. Which curl option is used to view the response header?
-I  flag to view the response headers

14. Which request method might an -I  flag to view the response headersattacker use to scope out usable HTTP requests that an HTTP server will accept?
They used the OPTIONS method

#### Sessions and Cookies

Recall that HTTP servers need ways to recognize clients from one another. These are implemented through sessions and cookies.

Answer the following questions about sessions and cookies.

15. Which response header sends a cookie to the client?

    ```HTTP
    HTTP/1.1 200 OK
    Content-type: text/html
    Set-Cookie: cart=Bob
    ```
Answer: Set-Cookie

16. Which request header sets a cookie in the client?

    ```HTTP
    GET /cart HTTP/1.1
    Host: www.example.org
    Cookie: cart=Bob
    ```
Answer: Cookie

#### Example HTTP Requests and Responses

Look through the following example HTTP request and response and answer the following questions.

#### HTTP Request Example

```HTTP
POST /login.php HTTP/1.1
Host: example.com
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Content-Type: application/x-www-form-urlencoded
Content-Length: 34
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Linux; Android 6.0; Nexus 5 Build/MRA58N) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3987.132 Mobile Safari/537.36

username=Barbara&password=password
```

17. What was the request method?
POST

18. Was the request encrypted or unencrypted?
Yes.

19. Does the request have a user session associated to it?
Yes

20. What kind of data is being sent from this request body.
Encoding: gzip, deflate, br

#### HTTP Response Example

```HTTP
HTTP/1.1 200 OK
Date: Mon, 16 Mar 2020 17:05:43 GMT
Last-Modified: Sat, 01 Feb 2020 00:00:00 GMT
Content-Encoding: gzip
Expires: Fri, 01 May 2020 00:00:00 GMT
Server: Apache
Set-Cookie: SessionID=5
Content-Type: text/html; charset=UTF-8
Strict-Transport-Security: max-age=31536000; includeSubDomains
X-Content-Type: NoSniff
X-Frame-Options: DENY
X-XSS-Protection: 1; mode=block

[page content]
```

21. What was the response status code?
200 OK

22. Was the response encrypted or unencrypted?
Unencrypted

23. Does this response have a user session associated to it?
No

24. What kind of content is likely to be in the [page content] response body?
gzip

25. If your class covered security headers, what security request headers have been included?
``
X-Content-Type: NoSniff
X-Frame-Options: DENY
X-XSS-Protection: 1; mode=block
``

#### Monoliths and Microservices

Answer the following questions about monoliths and microservices:

26. What are the individual components of microservices called?
* Properly scoped functionality. 
* Presenting an API. 
* Traffic management. 
* Data offloading. 
* Monitoring.

27. What is a service that writes to a database and communicates to other services?
APIs

28. What type of underlying technology allows for `microservices` to become scalable and have redundancy?
Docker containers allow for `microservices` to become scalable and have redundancy. Replication of components lets you serve more clients and
provides identical backup components if one fails.

#### Container Vulnerability Filtering

Answer the following questions about vulnerability filtering `Trivy` scans with `jq`:

29. Do `microservices` share the same kind of vulnerabilities as regular operating systems?
Yes.

30. Would an organization be more concerned with `Low` severity vulnerabilities as much as `Critical`?
Yes.

31. Would the bash tool `jq` be useful in finding certain kinds of vulnerabilities within a vulnerability report?
Yes. Some vulnerabilities we can report are (MITM), Buffer overflow, (DoS) and Privilege escalation.

#### Deploying and Testing a Container Set

Answer the following questions about multi-container deployment:

32. What is a tool that can be used to deploy multiple containers at once?
Docker Compose allows us to create repeated, multi-container deployments.

33. What kind of file format was required for us to deploy a container set?
Docker compose YAML file.

#### Container Runtime Intrusion Detection Systems

34. What is a tool used to actively detects intrusion behavior within containers?
Falco is an open-source CIDS that alerts security professionals to potential intrusion attempts.

35. What high-value system file might an intruder view that would trigger a `sensitive file opening` alert?
such as /etc/shadow

36. What kind of intruder action might trigger an alert from a container IDS that says `shell configuration file has been modified`?
such as `adduser`
---
