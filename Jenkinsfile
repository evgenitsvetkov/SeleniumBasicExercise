pipeline {
    agent any

    triggers {
        pollSCM('* * * * *')
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Restore dependencies') {
            steps {
                bat 'dotnet restore'
            }
        }
        stage('Build') {
            steps {
                bat 'dotnet build'
            }
        }
        stage('Run UI tests') {
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}