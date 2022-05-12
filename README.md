# CloudProject

## Description
This project was origonaly ment to deploy a website that would be able to lanch a container with a minecraft server on it and start the server.
### Current Project
 As of this point in the project I am able to do the following.
- Create a new resource group
- Create a App Service plan
- Create a App Service
- load a github repo into the new App Service
- Create a Container Instances with both a Public IP and port 25565 and 22 open
- load a docker image onto to Container instances
### Furture Plan
Start the Minecraft server from the website
This would be done by having a link/button on the website trigger a action to write to Service bus (like serverstart=1) this method will also be used to turn the server off. a logic app would then read the service bus and exicute a script that would then change the Service bus back to the origonal value and start the server. once the server was started another logic app would retrive the container's IP write it to a service bus and then display it on the website. I would as like to setup azure to send alerts when the server status is changed and at certain cost intervals. i would as like to look into saving the docker server files in a data base just in case the container fails.
### Well-Architected Framework Pillars
#### Cost Optimization
I used a Container for my server instead of a full vm because it was a 1/4 the price per month ($3.5 compared to $14).
I also used the free tier for my app service plan.
#### Reliablity
Reliablity is probably the second weakest link because as it stands none of the resources have fail over how every if a resource goes down the others could function mostly independent.
#### Operational Excellence
With the deployment of the resources being automated the chances of something going wrong is a lot lower.
#### Preformance Efficiency
I have none
#### Security
For security my website does require you to login however it is not curreny configured. As for the container the only port that are open on it by default.
