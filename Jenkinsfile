pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build / Publish') {
            steps {
                sh './gradlew publish'  // or './gradlew artifactoryDeploy'
            }
        }
    }
}
