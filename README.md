<b>SIMPLE CI FOR JAVA APP</b>


<b>Stack</b> <br>
![Jenkins Badge](https://camo.githubusercontent.com/f07984f16264bd6a4d8795653c37419551818e8aa338ae7fbf3b21ed057739c5/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4a656e6b696e732d4432343933393f7374796c653d666f722d7468652d6261646765266c6f676f3d6a656e6b696e73266c6f676f436f6c6f723d7768697465) ![Blue Ocean](https://img.shields.io/badge/-Blue%20Ocean-blue)<br>
![SonarQube Badge](https://camo.githubusercontent.com/b2614595460d3d5bb67e717f65e586365cc243adefaf6cb3c901f51f0b91f4ec/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f536f6e6172517562652d3445394243443f7374796c653d666f722d7468652d6261646765266c6f676f3d736f6e617271756265266c6f676f436f6c6f723d7768697465)<br>
![Groovy Badge](https://img.shields.io/badge/Groovy-%234298B8?style=for-the-badge&logo=groovy&logoColor=white)<br>
![Sonatype Nexus Badge](https://img.shields.io/badge/Sonatype%20Nexus-black?style=for-the-badge&logo=nexus&logoColor=white)<br>
![docker-compose](https://img.shields.io/badge/-docker--compose-blue) <br>


<b>Dependencies</b>
- vprofile-java-project:    https://github.com/jkb91jkb91/vprofile-project BRANCH:vp-rem   <br>
- jenkins-shared-libraries: https://github.com/jkb91jkb91/jenkins_repo.git BRANCH:shared_libraries   <br>
- ngrok isntalled          (required for GitHub hook trigger for GITScm polling)  <br>
- docker-compose installed (required for create network between jenkins,nexus,sonarqube) <br>  
- Dockerfile.jenkins <br>
- Dockerfile.sonarqube <br>
- Dockerfile.nexus <br>
- docker-compose.yml  <br>
<br>

<b>Installation</b>
- docker-compose up -d  <br>

<br>
<b>Preparation</b> <br>

 <br>


<b>Detailed steps</b> 
- Add slave agent( do not run on master)  <br>

- Install Plugin Slack  <br>
- Install Plugin SonarQube Scanner<br>
- Install Plugin Nexus Artifact Uploader  <br>

- Jenkins Credentials github keys to credentials <br>
- Jenkins Credentials add token from sonar
- 
- Jenkins Configure   Sonar (http://sonar:9000/ : "sonar" is the name used in docker-compose, - sonarToken_<br>
- Jenkins Configure   Nexus
- Jenkins Configure   Slack

- Jenkins Configure   Global Pipeline Libraries
  
- Start ngrok http 8080 <br>
- Jenkins create pipeline JOB and set GIt Poll SCM
- Github create Webhook based on ngrok URL



NEXT STEPS
1) Dodaj agenta
2) pomysl nad ssh key jak dodac
3) ogarnij sonara
4) ogarnij nexusa





<b>Author:Jakub Grzegorczyk </b> <br>
<b>Email: jakub.g26101991@gmail.com </b> <br>
