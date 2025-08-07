pipeline {
    agent any

    tools {
        maven 'maven-3.8.6'
        jdk 'jdk-17'
    }

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/RAVURILIKHITHA/maven.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
    }

    post {
        success {
            echo '✅ Build, Test and Clone Successful'
        }
        failure {
            echo '❌ Failed. Please check the logs.'
        }
    }
}

