pipeline {

    agent any
    
    tool name: 'gradle-6.4.1', type: 'gradle'

    stages {
        stage('Build') {
            steps {
                echo 'Checking out...'
                checkout scm

                echo 'Compiling...'
                withGradle {
                    sh "gradle init"
                }

                echo 'Building...'
                withGradle {
                    sh "gradle build"
                }

            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                withGradle {
                   sh "./gradlew.bat test"
                }
            }
        }
    }
}
