This package contains nginx reverse proxy and two sample service (apache and django).

 1. Add new network to docker (global network for reverse proxy)
`docker network create reverse_proxy_net`
1. Run apache container
`docker-compose -f apache_server/docker-compose.yml up`
2. Run django container
	* change project name in Dockerfile (line 14,15)
	* run `docker-compose -f django_app/docker-compose.yml up`
3. Run nginx container
	* if you want change services name in nginx.conf 
	* change server_name in nginx.conf to your domain name
	* run `docker-compose -f reverse_proxy/docker-compose.yml up`
4. If you don't have own domain, add to `/etc/hosts` file:  
	`127.0.0.1 apache`  
	`127.0.0.1 django`
5. Open in browser:
	* [apache/](http://apache/)
	* [django/](http://django/)
