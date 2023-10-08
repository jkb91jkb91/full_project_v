@Library('shared_library') _

pipeline {
    agent any
    tools {
        maven "MAVEN3"
    }
    
  environment {
    JDK_VERSION = 'OracleJDK8'
    JAVA_HOME = '/usr/local/jdk8'
    SONAR_TOKEN = credentials('sonarToken')
}

    stages {
        stage('fetch code') {
            steps {
                git branch: 'jenkins_sonar_nexus', url: "https://github.com/jkb91jkb91/vprofile_project/"
            }
        }
        
        stage('Build') {
            steps {
            script{
                    mavenBuild.execute()
            }
            }
            post {
                success {
                    archiveArtifacts artifacts: '**/*.war'
                }
            }
        }
        
        stage('Unit tests') {
            steps {
                script {
                    mavenUnitTests.execute()
                }
            }
        }

//        stage('SonarQube Analysis') {
 //           steps {
 //               script {
  //                  def scannerHome = tool name: 'sonar4.7', type: 'hudson.plugins.sonar.SonarRunnerInstallation'
   //                     withSonarQubeEnv('sonar') {
   //                         sh """
  //                              export JAVA_HOME=\"/opt/java/openjdk\"
  //                              ${scannerHome}/bin/sonar-scanner -X \
  //                              -Dsonar.projectKey=project_vprofile \
 //                              -Dsonar.projectName=vprofile \
 //                              -Dsonar.projectVersion=1.0 \
 //                              -Dsonar.sources=src/ \
//                              -Dsonar.java.binaries=target/test-classes/com/visualpathit/account/controllerTest/ \
//                             -Dsonar.junit.reportsPath=target/surefire-report/ \
 //                               -Dsonar.jacoco.reportsPath=target/jacoco.exec \
//                              -Dsonar.java.checkstyle.reportPaths=target/checkstyle-result.xml \
//                             -Dsonar.login=\$SONAR_TOKEN
 //                           """
 //                   }
  //              }
 //           }
 //       }

        stage('Send to ') {
            steps {
                  script {
                     slack.message('success')
              }
            }
     }
    

        stage('Upload Artifacts') {
            steps {
                script {
                    tool name: 'OracleJDK11', type: 'hudson.model.JDK'
                    nexusArtifactUploader(
                        nexusVersion: 'nexus3',
                        protocol: 'http',
                        nexusUrl: '172.17.0.2:8081',
                        groupId: 'QA',
                        version: '1',
                        repository: 'vprofile-repo',
                        credentialsId: 'nexus',
                        artifacts: [
                            [artifactId: 'projectName',
                             classifier: '',
                             file: 'target/vprofile-v1.war',
                             type: 'jar']
                        ]
                    )
                }
            }
        }
    }
}
