# Installation Neuvector (Version 1.3.0)

Installation of Neuvector 1.3.0 with Docker Enterprise 17.06

Login to your Master and install the Neuvector AllinOne solution by using docker run:
docker run -d --privileged --name allinone -e CLUSTER_JOIN_ADDR=172.16.1.4 -p 18300:18300 -p 18301:18301 -p 18400:18400 -p 18401:18401 -p 18301:18301/udp -p 8444:8443 -v /var/neuvector:/var/neuvector -v /var/run/docker.sock:/var/run/docker.sock -v /proc:/host/proc:ro -v /sys/fs/cgroup:/host/cgroup:ro neuvector/allinone:1.3.0 

Login to your Worker Nodes and install the Neuvector Enforcer by using docker run:
 docker run -d --privileged --name enforcer -e CLUSTER_JOIN_ADDR=172.16.1.4 -p 18301:18301 -p 18401:18401 -p 18301:18301/udp -v /var/neuvector:/var/neuvector -v /var/run/docker.sock:/var/run/docker.sock -v /proc:/host/proc:ro -v /sys/fs/cgroup:/host/cgroup:ro neuvector/enforcer:1.3.0
 
 Login to the admin web page on port 8444 via HTTPS. Please make sure this port is available on your firewall!
 
 Change the admin password via Settings > Profile > admin > Edit > Change password and timeout from 300 to 3600 (hour)

Enable AutoScan via - Vulnerabilities > AutoScan all




