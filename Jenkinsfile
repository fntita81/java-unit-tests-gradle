pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git url: 'https://github.com/fntita81/java-unit-tests-gradle.git'
            }
        }

        stage('Build') {
            steps {
                sh './gradlew clean build'
            }
        }

        stage('Test') {
            steps {
                sh './gradlew test'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'build/libs/*.jar', fingerprint: true
            }
        }
    } // <-- closes stages
} // <-- closes pipeline
