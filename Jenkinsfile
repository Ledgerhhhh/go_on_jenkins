pipeline {
    agent any

    environment {
        DOCKER_IMAGE_NAME = 'test_go_jenkins'
    }

    stages {
        stage('Checkout') {
            steps {
                // 检出代码
                checkout scm
            }
        }

        stage('Build') {
            steps {
                // 构建 Go 项目
                sh 'go build -o test_go_jenkins'
            }
        }

        stage('Build Docker Image') {
            steps {
                // 构建 Docker 镜像
                script {
                    docker.build(DOCKER_IMAGE_NAME)
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                // 运行 Docker 容器
                script {
                    docker.run(DOCKER_IMAGE_NAME)
                }
            }
        }
    }
}
