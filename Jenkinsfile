plugins {
    id 'java'
}

task clean(type: Delete) {
    delete rootProject.buildDir
}

pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }

        stage('Build') {
            steps {
                sh './gradlew clean build'
            }
        }

        stage('Publish Artifacts') {
            steps {
                sh './gradlew artifactoryPublish'
            }
        }
    }

    triggers {
        githubPush()
    }
}
