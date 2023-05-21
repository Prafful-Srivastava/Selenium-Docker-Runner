pipeline{
	agent any
	stages{
		stage("Run Tests"){
			steps{
				bat "docker-compose up"
			}
		}
		stage("Clean up"){
			steps{
				bat "docker-compose down"
			}
		}
	}
}