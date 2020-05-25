pipeline {

    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Checking out...'
                checkout scm

                echo 'Compiling...'
                sh "gradle init"

                echo 'Building...'
                sh "gradle build"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                "./gradlew clean test"
            }
        }
    }
}
