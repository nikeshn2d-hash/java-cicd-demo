pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                echo 'Checking out latest code...'
                checkout scm
            }
        }

        stage('Show Changes') {
            steps {
                echo 'Files changed in this push:'
                sh '''
                    git log -1 --stat
                '''
            }
        }

        stage('Build') {
            steps {
                echo 'Building application...'
                sh 'mvn clean package'
            }
        }

    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed!'
        }
    }
}
