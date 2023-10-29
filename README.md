**LIFT AND SHIFT PROJECT**




**HOW THIS APP WORKS**
1) Users requests APP by URL with HTTPS based by ACM
2) Request goes into ELB  
3) ELB routes traffic through port 8080 to TOMCAT instance(8080 is only allowed from Tomcat EC2 internally to ELB)  
4) Tomcat instance uses Autoscalling group for scale-in and scale-out  
5) Backend services are in different Security Group  
7) Backend services uses internal DNS zone on ROUTE53 to route traffic  

**PREREQUISUITES**  
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
-TOMCAT on 1 VM   >> will go on EC2  
-RabbitMQ on 1VM  >> will go on EC2  
-Memcache on 1VM  >> will go on EC2  
-MySQL    on 1 VM >> will go on EC2  
-NGINX    on 1 VM >> used ELB instead of NGINX  
