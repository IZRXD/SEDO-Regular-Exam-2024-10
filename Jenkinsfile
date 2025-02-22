pipeline {
    agent any
    environment {
        DOTNET_CLI_TELEMETRY_OPTOUT = '1'
    }
    stages {
        stage('Checkout') {
            steps {
                echo 'Checking out the code...'
                checkout scm
            }
        }
        stage('Restore Dependencies') {
            steps {
                echo 'Restoring dependencies...'
                bat 'dotnet restore HouseRentingSystem.sln'
            }
        }
        stage('Build') {
            steps {
                echo 'Building the application...'
                bat 'dotnet build HouseRentingSystem.sln --configuration Release'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'dotnet test HouseRentingSystem.sln --configuration Release --no-build --verbosity normal'
            }
        }
    }
}
