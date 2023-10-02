pipeline{
        agent any
        tools {
                maven 'mavan-3.6'
        }
        stages {
                stage("build jar") {
                        steps {
                                script {
                                        echo "building the application..."
                                        sh 'mvn package'
                                }
                        }
                }
                stage {
                        steps {
                                script {
                                        echo "building the docker image..."
                                        withCredentials([usernamePassword(credentialsId: 'docker-hub-repo', passwordVariable: 'PASS', usernameVariable: 'USER')]) {
                                        sh 'docker build -t aksxy/demo-app:jma-2.0 .'
                                        sh "echo $PASS | docker login -u $USER --password-stdin"
                                        sh 'docker push aksxy/demo-app:jma-2.0'
                                        }
                                }
                        }
                }
                stage("deploy") {
                        steps {
                                script {
                                        echo "deploying the application..."
                                }
                        }
                }
        }
}
