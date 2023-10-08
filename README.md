<b>SIMPLE CI FOR JAVA APP</b>


Stack<br>
![Jenkins Badge](https://camo.githubusercontent.com/f07984f16264bd6a4d8795653c37419551818e8aa338ae7fbf3b21ed057739c5/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f4a656e6b696e732d4432343933393f7374796c653d666f722d7468652d6261646765266c6f676f3d6a656e6b696e73266c6f676f436f6c6f723d7768697465)<br>
![SonarQube Badge](https://camo.githubusercontent.com/b2614595460d3d5bb67e717f65e586365cc243adefaf6cb3c901f51f0b91f4ec/68747470733a2f2f696d672e736869656c64732e696f2f62616467652f536f6e6172517562652d3445394243443f7374796c653d666f722d7468652d6261646765266c6f676f3d736f6e617271756265266c6f676f436f6c6f723d7768697465)<br>
![Groovy Badge](https://img.shields.io/badge/Groovy-%234298B8?style=for-the-badge&logo=groovy&logoColor=white)<br>
![Sonatype Nexus Badge](https://img.shields.io/badge/Sonatype%20Nexus-black?style=for-the-badge&logo=nexus&logoColor=white)<br>

<b>Dependencies</b>
vprofile-java-project:    https://github.com/jkb91jkb91/vprofile-project BRANCH:vp-rem
jenkins-shared-libraries: https://github.com/jkb91jkb91/jenkins_repo.git BRANCH:shared_libraries
ngrok(required for GIT POLL)
Docker Image: jenkins, nexus, sonarqube

<b>Installation:</b>
Jenkins: docker run -p 8080:8080 -p 50000:50000 -v /home/jkb91/Documents/jenkins_docs:/var/jenkins_home jenkins/jenkins:lts <br>
Sonarqube: <br>
Nexus: <br>


<b>Preparation</b>
Jenkins
- Add slave agent( do not run on master)
- Install Plugin Slack:                   Configure "Slack"
- Install Plugin SonarQube Scanner:       Configure "Sonarqube"
- Install Plugin Nexus Artifact Uploader: Configure "Nexus"
- Configure  "Global Pipeline Libraries"


Author:Jakub Grzegorczyk
Email: jakub.g26101991@gmail.com
