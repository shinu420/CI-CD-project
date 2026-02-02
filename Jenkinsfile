pipeline {
    agent any

    environment {
        APP_NAME = "ci-cd-demo"
        IMAGE_NAME = "ci-cd-demo:latest"
        CONTAINER_NAME = "ci-cd-container"
    }

    stages {

        stage('Checkout Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/shinu420/ci-cd-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t $IMAGE_NAME .'
            }
        }

        stage('Stop Old Container') {
            steps {
                sh '''
                if [ "$(docker ps -q -f name=$CONTAINER_NAME)" ]; then
                    docker stop $CONTAINER_NAME
                    docker rm $CONTAINER_NAME
                else
                    echo "No existing container"
                fi
                '''
            }
        }

        stage('Run New Container') {
            steps {
                sh '''
                docker run -d \
                --name $CONTAINER_NAME \
                -p 5000:5000 \
                $IMAGE_NAME
                '''
            }
        }
    }

    post {
        success {
            echo "✅ Deployment successful!"
        }
        failure {
            echo "❌ Deployment failed!"
        }
    }
}
