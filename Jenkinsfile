pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Build and Deploy') {
            steps {
                sh '''
                    # Docker Compose 빌드 및 재시작
                    docker-compose -f /path/to/docker-compose.yml up -d --build
                    
                    # 사용하지 않는 이미지 정리
                    docker image prune -f
                '''
            }
        }
    }
    
    post {
        success {
            echo 'Deployment successful!'
        }
        failure {
            echo 'Deployment failed!'
        }
    }
}
