pipeline {
    agent none
        
    
    environment {DOTNET_CLI_HOME = "/tmp/dotnet_cli_home"}
    stages {
        stage('Build'){
            agent {        
                docker  { image 'mcr.microsoft.com/dotnet/sdk:6.0' }
            }
            steps {
                sh 'dotnet build' 
                sh 'dotnet test'
            }

        }
        stage('TypeScript'){
            agent {        
                docker  { image 'node:17-bullseye' }
            }
            steps {
                dir("DotnetTemplate.Web"){
                    sh 'npm install' 
                    sh 'npm run lint'
                    sh 'npm t'
                }
            }

        }

 
}
}