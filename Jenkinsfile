pipeline {
    agent any
    tools {
        maven 'maven-3.6'
    }
    stages {
        stage("Build Jar") {
            steps {
                script {
                    echo "Building the application..."
                    sh 'mvn package'
                }
            }
        }
        stage("Build Docker Image") {
            steps {
                script {
                    echo "Building the Docker image..."
                    withCredentials([usernamePassword(credentialsId: 'docker-hub-repo', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
                        sh 'docker build -t aksxy/demo-app:jma-2.0 .'
                        sh "echo $PASS | docker login -u $USER --password-stdin"
                        sh 'docker push aksxy/demo-app:jma-2.0'
                    }
                }
            }
        }
        stage("Deploy") {
            steps {
                script {
                    echo "Deploying the application..."
                }
            }
        }
    }
}
