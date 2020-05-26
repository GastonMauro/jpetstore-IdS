pipeline {

    agent any
    
    tools{
        jdk 'jdk-11'
        gradle 'Default'
    }
    
    environment{
        GRADLE_VERSION = 'Default'
    }
    
    stages {
        stage('Build') {
            steps {
                echo 'Checking out...'
                checkout scm

                echo 'Compiling...'
                withGradle{
                    sh "gradle init"
                }

                echo 'Building...'
                withGradle{
                    sh "gradle build"
                }

            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                withGradle{
                   //sh "./gradlew.bat test"
                    sh "gradle test"
                }
            }
        }
    }
}
