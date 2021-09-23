pipeline {
    agent none

    stages {
        stage('Build .NET') {
            agent {
                docker { image 'mcr.microsoft.com/dotnet/sdk' }
            }
            steps {
                echo 'Building..'
            }
        }
        stage('Build Node') {
            agent {
                docker { image 'node:16-alpine' }
            }
            steps {
                echo 'Building Node..'
            }
        }
    }
}
