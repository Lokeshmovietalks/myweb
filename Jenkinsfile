@Library ('sharedlib') _
pipeline{
  agent any
  stages{
    stage("SCM Checkout"){
        steps{
            git 'https://github.com/Lokeshmovietalks/myweb'
        }
    }
    stage("Maven Build"){
      steps{
        sh 'mvn clean package'
        sh 'mv target/myweb*.war target/myweb.war'
      }
    }
    stage("Tomcat Deploy"){
      steps{
        tomcat("tomcat-server","myweb","ec2-user","172.31.2.110")
      }
    }
  }
}
