pipeline {
    agent any
    stages {
      stage('Checkout') {
            steps {
                echo 'Building the application...'
                checkout scm
            }
        }
      stage('Restore Dependencies') {
            steps {
                echo 'Building the application...'
                bat 'dotnet restore' 
            }
        }
        stage('Build') {
            steps {
                echo 'Building the application...'
                bat 'dotnet build' 
            }
        }
        stage('Test') {
            steps {
                echo 'Executing tests...'
                bat 'dotnet test' 
            }
        }
    }
}
