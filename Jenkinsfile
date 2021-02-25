pipeline {
    agent none
    environment {
        DOTNET_CLI_HOME = '/tmp'
        }
    stages {
        stage('dotnet') {
            agent {
                docker { image 'mcr.microsoft.com/dotnet/sdk:5.0' }
            }
            steps {
                sh 'dotnet build'
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