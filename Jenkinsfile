pipeline {
    agent none
        
    }
    stages {
        stage('Build')
        agent {        
            docker  { image 'mcr.microsoft.com/dotnet/sdk:6.0' }
        }
            steps {
                sh 'dotnet build' 
            }
        }
        stage('TypeScript') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}