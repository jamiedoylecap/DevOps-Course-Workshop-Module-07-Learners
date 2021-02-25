pipeline {
    agent none
    environment {
        DOTNET_CLI_HOME = '/tmp'
        }
    stages {
        stage('dotnet') {
            agent {
                docker { image 'mcr.microsoft.com/dotnet/sdk:3.1' }
            }
            steps {
                sh 'echo DOTNET'
                sh 'dotnet build && dotnet test'
            }
        }
        stage('NPM') {
            agent {
                docker { image 'node:14-alpine' }
            }
            steps {
                sh 'node --version'
                sh 'cd DotnetTemplate.Web && npm install && npm run build'
            }
        }
    }
    
}