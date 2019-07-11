pipeline{
        agent any
        stages{
		stage('Invest'){
			steps{
				sh "pwd"
				sh "ls -alrt"
			}
		}
                stage('Build Client and Server'){
                        steps{
                                sh "docker-compose build --no-cache"
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

