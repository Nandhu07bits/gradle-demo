pipeline {
    agent any

    stages {
        stage('Checkout') { // Task 2, Step 3 [cite: 70]
            steps {
                checkout scm
            }
        }

        stage('Build & Test') { // Task 2, Step 3 [cite: 71]
            steps {
                // Uses Gradle for build and test execution [cite: 68]
                sh 'gradle clean test'
            }
        }

        stage('Archive Artifact') { // Task 2, Step 3 [cite: 73]
            steps {
                sh 'gradle jar'
                // Archive the generated JAR for Jenkins UI download [cite: 74, 75]
                archiveArtifacts artifacts: 'build/libs/*.jar', fingerprint: true
            }
        }
    }
}
