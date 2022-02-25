pipeline{
    agent any
    triggers {
      pollSCM '* * * * *'
    }
    stages{
        stage("Maven Build"){
            when {
                branch "develop"
            }
            steps{
               sh "mvn package"
            }
        }
        stage("SonarQube Analysis"){
            when {
                branch "develop"
            }
            steps{
               withSonarQubeEnv('sonar7') {
                    sh "mvn sonar:sonar"
               }
            }
        }
    }
}