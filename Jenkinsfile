@Library("sharedlibs") _
pipeline {
  agent any
  tools {
    maven 'maven3'
  }
  stages{
    stage("Maven Build"){
      steps{
        sh "mvn clean package"
        sh "mv myweb*.war myweb.war"
      }
    }
    stage("Deploy To Dev"){
      steps{
        tomcat("tomcat-dev","myweb","ec2-user",172.31.2.110)
      }
    }
  }
}
