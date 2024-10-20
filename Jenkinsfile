@Library('sharedlib') _
pipeline{
    agent any
    stages{
        stage("SCM build"){
            steps{
                git 'https://github.com/Lokeshmovietalks/myweb'
            }
        }
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
