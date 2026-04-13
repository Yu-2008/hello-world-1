pipeline {
    agent any

    tools {
        gradle 'Gradle-9'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/Yu-2008/hello-world-1.git'
            }
        }

        stage('Build') {
            steps {
                bat 'gradle clean build'
            }
        }

        stage('Test') {
            steps {
                bat 'gradle test'
            }
        }

        stage('Deploy') {
            steps {
                powershell 'java -jar build/libs/hello-world-java-V1.0.jar'
            }
        }
    }

    post {
        always {
            echo 'Cleaning up workspace'
            deleteDir()
            echo 'Workspace directory deleted!!!!!!!!! >^< ^^ =^= 3.3 Orz'
        }
        success {
            echo 'Build succeeded!!!'
        }
        failure {
            echo 'Build failed!'
        }
    }
}