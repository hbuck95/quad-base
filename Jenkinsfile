pipeline{
        agent any
        stages{
                stage('---build server---'){
                        steps{
                                sh "docker build ./server -t localhost:5000/server:latest"
                        }
                }
                stage('---build client---'){
                        steps{
                                sh "docker build ./client -t localhost:5000/client:latest"
                        }
                }
		stage('--push server--'){
                        steps{
                                sh "docker push localhost:5000/server:latest"
                        }
                }
		stage('---push client---'){
                        steps{
                                sh "docker push localhost:5000/client:latest"
                        }
              }
        }
}
