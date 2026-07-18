pipeline {
    agent any

    tools {
        maven 'Maven'
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/nikeshn2d-hash/java-cicd-demo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

    }

    post {

        success {
            echo 'Application Built Successfully!'
        }

        failure {
            echo 'Build Failed!'
        }

    }
}