pipeline {
    agent any
    environment {
        DOTNET_CLI_TELEMETRY_OPTOUT = '1'
    }
    stages {
        
        stage('Restore Dependencies') {
            steps {
                echo 'Restoring dependencies...'
                bat 'dotnet restore'
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
