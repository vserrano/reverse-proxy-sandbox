# NGINX

NGINX is configured to serve as a reverse proxy and the generated logs will display its performance metrics.

# Server
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

# Services

## /http/*
Reverse proxy for https://httpstat.us which provides a useful set of HTTP responses from testing.

Examples:
 - Get an HTTP/200 response: http://localhost:8081/http/200
 - Get an HTTP/300 response: http://localhost:8081/http/300
 - Get a delayed response of 3 seconds: http://localhost:8081/http/200?sleep=3000

For more information: https://httpstat.us/
