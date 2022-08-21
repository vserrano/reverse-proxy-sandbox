# reverse-proxy-sandbox
Contains a few tests and experiments with reverse proxies.

Each reverse proxy and it's configuration is in a Docker container and managed by Docker Compose.

# Requirements

A machine with Docker installed and configured for Docker Compose. Linux OS is preferred.

# NGINX

NGINX is configured to serve as a reverse proxy and the generated logs will display its performance metrics.

NGINX listens to the port 8081 on the localhost.

## Log configuration
The access logs are configured to output in a CSV format to easily retrieve the metrics. The format is as follows:
 - Local time
 - Upstream connect time
 - Upstream response time
 - Request time
 - HTTP Status code
 - Bytes sent
 - Upstream bytes received
 - HTTP Request to the proxy

## Services

### /http/*
Reverse proxy for https://httpstat.us which provides a useful set of HTTP responses from testing.

Examples:
 - Get an HTTP/200 response: http://localhost:8081/http/200
 - Get an HTTP/300 response: http://localhost:8081/http/300
 - Get a delayed response of 3 seconds: http://localhost:8081/http/200?sleep=3000

For more information: https://httpstat.us/

# HTTPD

Apache HTTPD is configured to serve as a reverse proxy and it is listening to the port 8082.

## Log configuration
Apache logs are configured to display performance information. There is less information to display out-of-the-box compared to NGINX. The available logs in CSV format are:
 - Time of the request
 - Time to fulfill the request in seconds
 - Time to fulfill the request in microseconds
 - HTTP return status code
 - Size of the response in bytes excluding HTTP headers
 - Host

## Services

### /http
Reverse proxy for https://httpstat.us which provides a useful set of HTTP responses from testing.

Examples:
 - Get an HTTP/200 response: http://localhost:8081/http/200
 - Get an HTTP/300 response: http://localhost:8081/http/300
 - Get a delayed response of 3 seconds: http://localhost:8081/http/200?sleep=3000

For more information: https://httpstat.us/
