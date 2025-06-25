pipeline {
    agent any

    stages {
        stage('Checkout the repo') {
            steps {
                checkout scm
            }
        }

        stage('Restore dependencies') {
            steps {
                powershell 'dotnet restore'
            }
        }

        stage('Build') {
            steps {
                powershell 'dotnet build --no-restore'
            }
        }

        stage('Test') {
            steps {
                powershell 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
