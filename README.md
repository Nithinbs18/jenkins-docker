# Creating a custom Jenkins with docker-in-docker

This repository has contents to launch Jenkins's custom image with docker.

Using this image you can launch Jenkins with HTTPS and ModSecurity web application firewall in minutes.

## Steps:

1. Create a reverse-proxy environment with Nginx.

To have automated Nginx configured we user docker-gen, for auto SSL we use the letsencrypt-companion and finally for the web application firewall we use the ModSecurity image
You can do it by simply cloning the repository https://github.com/Nithinbs18/nginx-modsec-dockergen-letsencrypt and running it.

2. Launch Jenkins with docker using this repository.

The environment variables must be changed accordingly as per your requirement for the functioning of the application.
To access docker inside the Jenkins docker container which is quite common we mount the docker.sock from the host machine to the container.

3. Change permission of /var/run/docker.sock on the host machine to access it inside the Jenkins container.

You can do that by finding out the id of Jenkins user inside the container and changing it accordingly on the host machine using the "chown" command.
