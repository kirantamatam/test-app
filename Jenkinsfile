pipeline{
    agent any
    stages{
        stage("mvn package"){
            when{ branch 'develop'}
            steps{
                echo " building maven package..."
            }
        }
        stage("sonarqube"){
            when{ branch 'develop'}
            steps{
                echo " sonarqube analysis..."
            }
        }
        stage("nexus"){
            when{ branch 'develop'}
            steps{
                echo " uploading atifacts..."
            }
        }
        stage("analysis"){
            when{ branch 'qa'}
            steps{
                echo " quality checking... "
            }
        }
        stage("deployment"){
            when{ branch 'master'}
            steps{
                echo " deploying to prod..."
            }
        }
        
    }
}