pipeline {
    agent none
        
    }
    environment {DOTNET_CLI_HOME = "/tmp/dotnet_cli_home"}
    stages {
        stage('Build')
        agent {        
            docker  { image 'mcr.microsoft.com/dotnet/sdk:6.0' }
        }
            steps {
                sh 'dotnet build' 
            }

            steps {
                sh 'dotnet test' 
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