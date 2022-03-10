# segment
Migrate GO redirector to Nginx

## Healthy check port 443

Import crt from local path

## Segment use 3 locations

analytics -> location ~ ^/analytics.js/v1/

proxy_pass https://cdn.segment.com;

projects -?> location ~ ^/v1/projects

proxy_pass https://cdn.segment.com;

default -> location  ~ ^/

proxy_pass https://api.segment.io;


Important lines

**Set real user ip**

*proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;*

**Set domain in the Forwarder**

*proxy_set_header Forwarded "segment.midoamin.net";*


