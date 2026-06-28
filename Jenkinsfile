pipeline {
    agent any

    environment {
        DEPLOY_DIR = "/home/ubuntu/svgv"
    }

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/your-username/your-repository.git'
            }
        }

        stage('Build') {
            steps {
                echo "Building application"

                sh """
                    mkdir -p ${DEPLOY_DIR}
                """
            }
        }

        stage('Deploy') {
            steps {
                sh """
                    echo "Deploying application..."

                    cp -r * ${DEPLOY_DIR}/

                    echo "Deployment completed."
                """
            }
        }
    }

    post {
        success {
            echo "Deployment Successful"
        }

        failure {
            echo "Deployment Failed"
        }
    }
}
