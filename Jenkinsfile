pipeline {
    agent any

    stages {
        stage('Restore Dependencies') {
            when {
                branch 'feature-ci-pipeline'
            }
            steps {
                bat 'dotnet restore'
            }
        }

        stage('Build application') {
            when {
                branch 'feature-ci-pipeline'
            }
            steps {
                bat 'dotnet build --no-restore'
            }
        }

        stage('Run Tests') {
            when {
                branch 'feature-ci-pipeline'
            }
            steps {
                bat 'dotnet test --no-build --verbosity normal'
            }
        }
    }
}
