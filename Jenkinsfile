pipeline {
    agent none
    stages {
        stage('dotnet') {
            agent {
                docker { image 'mcr.microsoft.com/dotnet/sdk:5.0' }
            }
            steps {
                sh 'ls -all'
                sh 'pwd'
                sh 'whoami'
            }
        }
        stage('NPM') {
            agent {
                docker { image 'node:14-alpine' }
            }
            steps {
                sh 'node --version'
                sh 'npm install'
            }
        }
    }
    
}