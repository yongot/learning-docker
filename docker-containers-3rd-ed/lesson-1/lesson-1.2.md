# 1.2 Understand how containers change applications

## Example: Install and Run Web Server (Package)
- Get httpd package and install to host `yum install httpd`
- Copy content `cp -r <files> /var/www/html/`
- Start service `systemctl start httpd`

## Package / Deploy Applications (Containerized)
- Application bundled with dependencies in container image
- docker pull or run gets container iamge from registry
- image stored locally (not intalled) in /var/lib/docker/
- container executes as instructed
- service daemon (by default)
  - listens to ports on container network
  - accesses content within container (or mounted from host)
  - access to container processes table and IPC (host ps also)
  
## Example: Install and Run Web Server (Container)
- Pull container to local system and store under /var/lib/docker `docker pull myhttpd`
- Copy content `cp -r <files> /var/www/html/`
- Start container `docker run -d -v /var/www/:/var/www -P myhttpd`

## Observing How Containers Work
- containers developers put together most of the pieces
- software stays together and is less dependent on host
- arrangements needed to store content and store service
- removing the container is easier because:
  - content isn't installed across the host
  - data are stored separate from application
- containerizing an application makes it so
  - incompatible apps can run on the same host
  - host system can remain more generic

