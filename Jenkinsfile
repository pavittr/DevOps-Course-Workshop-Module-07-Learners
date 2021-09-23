pipeline {
    agent none

    stages {
        stage('Build .NET') {
            agent {
                docker { image 'mcr.microsoft.com/dotnet/sdk' }
            }
            steps {
                echo 'Building..'
                sh 'dotnet build'
                sh 'dotnet test'
            }
        }
        stage('Build Node') {
            agent {
                docker { image 'node:16-alpine' }
            }
            steps {
                echo 'Building Node..'
                sh 'npm install'
                sh 'npm run build'
                sh 'npm t'
                sh 'npm run lint'
            }
        }
    }
}
