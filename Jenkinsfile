pipeline {

    agent any
    
    tools{
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
                withGradle(gradle: GRADLE_VERSION){
                    sh "gradle init"
                }

                echo 'Building...'
                withGradle(gradle: GRADLE_VERSION){
                    sh "gradle build"
                }

            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                withGradle(gradle: GRADLE_VERSION){
                   sh "./gradlew.bat test"
                }
            }
        }
    }
}
