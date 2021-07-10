# Pingdom Website Speed Test
> [Testing Site](https://tools.pingdom.com/)
## Result
![](https://i.imgur.com/au1Jxsv.png)

## How to improve page load speed?
1. Enable nginx gzip.
```
gzip on;
gzip_buffers 4 16k;
gzip_comp_level 6;
gzip_vary on;
gzip_types text/plain text/css application/json application/x-javascript text/xml application/xml application/xml+rss text/javascript;
```
2. Increase bandwidth, suppose 1 Mbit/s bandwidth page download time is 2.9/0.125 = 23.2 sec, higher bandwidth will improve download speed.
## Back End Enable Gzip
After enable gzip will reduce transmission data size.
![](https://i.imgur.com/Dw9KgpX.png)
```go=
import "github.com/gorilla/handlers"
...
log.Fatalln(http.ListenAndServeTLS(..., handlers.CompressHandler(s)))
```
