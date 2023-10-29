**LIFT AND SHIFT PROJECT**




**HOW THIS APP WORKS**
1) Users requests APP by URL with HTTPS based by ACM
2) Request goes into ELB  
3) ELB routes traffic through port 8080 to TOMCAT instance(8080 is only allowed from Tomcat EC2 internally to ELB)  
4) Tomcat instance uses Autoscalling group for scale-in and scale-out  
5) Backend services are in different Security Group  
7) Backend services uses internal DNS zone on ROUTE53 to route traffic  

**PREREQUISUITES**  
-Maven 3. and Java11 installed locally  
-Locally prepared application ready to build with maven  
-Scripts for Tomcat,MySQL,MemCached,RabbitMQ
-Created certificate for HTTPS > ACM  
-Installed AWS CLI locally for S3 bucket connection  
-Domain bought on GoDaddy.com (devopsproject.pl)  

***USED TECHNOLOGIES ON AWS***
-AWS CLI && IAM 
-ACM  
-EC2 x 4  
-AutoScalling Service for EC2  
-S3 Bucket  
-ROUTE53 (internal DNS for backend)  
-ELB
-Cloudformation

**OUR BASE APP**  
-TOMCAT on 1 VM   >> will go on EC2  together with LA (ELB instead of NGINX will be used) (frontend SG)  
-RabbitMQ on 1VM  >> will go on EC2  (backend SG)  
-Memcache on 1VM  >> will go on EC2  (backend SG)  
-MySQL    on 1 VM >> will go on EC2  (backend SG)  
  


**STEPS** 
- CREATE KEY-PARIS for connection with all EC2 instances  
- CREATE SECURITY GROUPS  (frontend, backend, loadbalancer)
- Create EC2 instances with provided scripts in this repo
- Configure ROUTE53  with internal DNS ZONE  
   in application properties > provide domains for mysql,memcached,rabbitmq and save the file
-Build the app with maven and upload S3 bucket


  

-
