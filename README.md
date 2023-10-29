**LIFT AND SHIFT PROJECT**


**PREREQUISUITES**  
Created certificate for HTTPS > ACM  
Installed AWS CLI locally  
Domain bought on GoDaddy.com (devopsproject.pl)  

***USED TECHNOLOGIES ON AWS***
AWS CLI && IAM 
ACM  
EC2 x 4  
AutoScalling Service for EC2  
S3 Bucket  
ROUTE53 (internal DNS for backend)  
ELB
Cloudformation

**OUR BASE APP** 
TOMCAT on 1 VM   >> will go on EC2  
RabbitMQ on 1VM  >> will go on EC2  
Memcache on 1VM  >> will go on EC2  
MySQL    on 1 VM >> will go on EC2  
NGINX    on 1 VM >> used ELB instead of NGINX  
