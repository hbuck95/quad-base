pipeline{
        agent any
        stages{
                stage('Build Server'){
                        steps{
                                sh "docker build ./server -t localhost:5000/server:latest"
                        }
                }
                stage('Build Client'){
                        steps{
                                sh "docker build ./client -t localhost:5000/client:latest"
                        }
                }
		stage('Push Server'){
                        steps{
                                sh "docker push localhost:5000/server:latest"
                        }
                }
		stage('Push Client'){
                        steps{
                                sh "docker push localhost:5000/client:latest"
                        }
                }
		stage('Deploy'){
			steps{
				sh "docker-compose up -d"
			}
		}
        }
}
