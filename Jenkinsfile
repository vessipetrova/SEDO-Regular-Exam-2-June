pipeline {
    agent any
    triggers {
        githubPush()
    }
    stages {
        stage('Get from Git') { 
            steps {
                checkout scm
            }
        }
        stage('Restore .NET Depends') {
              steps {
                sh 'dotnet restore' 
              }
        }
        stage('Build .NET') {
            steps {
                sh 'dotnet build --no-restore' 
            }
        }
        stage('Test .NET') {
            steps {
                sh 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
