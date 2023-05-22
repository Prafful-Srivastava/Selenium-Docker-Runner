pipeline{
	agent any
	stages{
		stage("Start Grid"){
			steps{
				bat "docker-compose up -d hub chrome firefox"
			}
		}
		stage("Run Tests"){
			steps{
				bat "docker-compose up search-module book-flight-module"
			}
		}
		stage("Clean up"){
			steps{
				bat "docker-compose down"
			}
		}
	}
}