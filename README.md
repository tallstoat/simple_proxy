# simple_proxy
Simple lightweight python http debugging proxy to help track REST or SOAP web services problems.

Set the following environment variables :-

* export PROXY_LOCAL, (localhost:8880 by default)

* export PROXY_TARGET, the port is 80 by default

* export PROXY_SSL=1 if target has to be reached using ssl, the default port becomes 443

* export PROXY_TRACE=true to turn on tracing

Here is an example :-

```
export PROXY_LOCAL=localhost:8089
export PROXY_TARGET=localhost:8082
export PROXY_TRACE=true
```

NOTE: This utility requires Python3.

Then run `python3 simple_proxy.py` to forward all incoming request on PROXY_LOCAL (always http) to PROXY_TARGET (http/https).

HTTP packets are unchanged except for references to PROXY_LOCAL replaced by PROXY_TARGET to ensure 100% transparent proxy behavior (a true man-in-the-middle behavior :-) even in gzip compressed bodies)
