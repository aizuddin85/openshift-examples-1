# Nginx reverse proxy

Based on http://keyangxiang.com/2018/06/01/Openshift/how-to-run-nginx-as-reverse-proxy/



oc new-build openshift/nginx~https://github.com/rbo/openshift-examples.git#nginx --name=nginxbase --context-dir=nginx-reverse-proxy --strategy=source


oc new-app https://github.com/rbo/openshift-examples.git#nginx --context-dir=nginx-reverse-proxy --strategy=docker --name=reverse-proxy
oc expose svc/reverse-proxy
