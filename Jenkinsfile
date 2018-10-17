pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
            post {
                success{
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: 'webapp/**target/*.war'
                }
            }
        }
        stage('Deploy to Staging')
        {
            build job: 'deploy-to-stagin'
        }
    }    
}
