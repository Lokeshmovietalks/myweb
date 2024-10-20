@Library('sharedlib') _
pipeline{
    agent any
    stages{
        stage("Maven Build"){
            steps{
                sh 'mvn clean package'
            }
        }
        stage("Nexus Deployment"){
            steps{
                script{
                    tomcat.nexus("myweb","Nexus")
                }
            }
        }
    }
}
