<b>SIMPLE CI FOR JAVA APP</b>


Stack<br>
![Jenkins Badge](https://camo.githubusercontent.com/f07984f16264bd6a4d8795653c37419551818e8aa338ae7fbf3b21ed057739c5/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4a656e6b696e732d4432343933393f7374796c653d666f722d7468652d6261646765266c6f676f3d6a656e6b696e73266c6f676f436f6c6f723d7768697465)<br>
![SonarQube Badge](https://camo.githubusercontent.com/b2614595460d3d5bb67e717f65e586365cc243adefaf6cb3c901f51f0b91f4ec/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f536f6e6172517562652d3445394243443f7374796c653d666f722d7468652d6261646765266c6f676f3d736f6e617271756265266c6f676f436f6c6f723d7768697465)<br>
![Groovy Badge](https://img.shields.io/badge/Groovy-%234298B8?style=for-the-badge&logo=groovy&logoColor=white)<br>
![Sonatype Nexus Badge](https://img.shields.io/badge/Sonatype%20Nexus-black?style=for-the-badge&logo=nexus&logoColor=white)<br>
![docker-compose](https://img.shields.io/badge/-docker--compose-blue) <br>


<br>
<br>
<br>
<b>Dependencies</b> <br>
Repositories <br>
- vprofile-java-project:    https://github.com/jkb91jkb91/vprofile-project BRANCH:vp-rem   <br>
- jenkins-shared-libraries: https://github.com/jkb91jkb91/jenkins_repo.git BRANCH:shared_libraries   <br>
Installation <br>
- ngrok isntalled          (required for GitHub hook trigger for GITScm polling)  <br>
- docker-compose installed (required for create network between jenkins,nexus,sonarqube) <br>  
Docker Images <br>
- Dockerfile.jenkins <br>
- Dockerfile.sonarqube <br>
- Dockerfile.nexus <br>
Docker Compose <br>
- docker-compose.yml  <br>

<br>
<br>

<b>Installation</b> <br>
docker-compose up -d  <br>

<br>
<b>Preparation</b> <br>
- Add slave agent( do not run on master)
- Install Plugin Slack
- Install Plugin SonarQube Scanner<br>
- Install Plugin Nexus Artifact Uploader



Detailed steps <br>
- Start ngrok http 8080 <br>
- Jenkins Credentials github keys to credentials <br>
- Jenkins Configure   Sonar (http://sonar:9000/ : "sonar" is the name used in docker-compose, - sonarToken_<br>
- Jenkins Configure   Nexus
- Jenkins Configure   Global Pipeline Libraries
- Jenkins Configure   Slack





Author:Jakub Grzegorczyk <br>
Email: jakub.g26101991@gmail.com <br>
