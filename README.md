# ansiproject
roles, tasks, loops, adhoc, gathering facts, handlers, tags

# Loadbalancer
```
after setting up the loadbalancer run the below command to check the output

ansible 172.31.11.3 -m command -a "cat /etc/nginx/nginx.conf" --become

the output should be:

172.31.11.3 | CHANGED | rc=0 >>
events {}
http {
    upstream backend {
                    server 172.31.38.9:8080;
                    server 172.31.11.3:8080;
             }
 server {
   listen 80;
   location / {
     proxy_pass  http://backend;
   }
 }
}


```
