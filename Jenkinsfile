pipeline {
    agent any
    stages {
        stage('Build') { 
            steps {
                sh 'dotnet restore' 
                sh 'dotnet build --no-restore' 
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
