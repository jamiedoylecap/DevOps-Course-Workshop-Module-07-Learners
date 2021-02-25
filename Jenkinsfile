pipeline {
    agent none
    stages {
        stage('dotnet') {
            agent {
                docker { image 'mcr.microsoft.com/dotnet/sdk:5.0' }
            }
            steps {
                sh 'ls'
                sh 'pwd'
            }
        }
    }
}