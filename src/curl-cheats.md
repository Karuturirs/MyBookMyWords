## Curl Cheats

#### Only response body

>  curl -X GET http://www.google.com


#### Only response headers

> curl -sD - -o /dev/null  http://www.google.com

#### Only Response time

> curl -o /dev/null -s -w %\{time_total\}\\n  https://www.google.com


