pipeline {

    agent any
    
    tools{
        gradle 'gradle-6.4.1'
    }
    
    environment{
        GRADLE_VERSION = 'gradle-6.4.1'
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
