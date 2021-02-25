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
                sh 'ls -all'
                sh 'pwd'
                sh 'dotnet build'
            }
        }
        stage('NPM') {
            agent {
                docker { image 'node:14-alpine' }
            }
            steps {
                sh 'node --version'
                sh 'npm install'
                sh 'npm run build'
            }
        }
    }
    
}