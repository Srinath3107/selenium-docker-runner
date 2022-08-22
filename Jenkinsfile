pipeline{
	agent any
	stages{
		stage('Pull Latest Image'){
			steps{
				//sh "docker pull srinathpalakonda/selenium-docker"
				bat "docker pull srinathpalakonda/selenium-docker"
			}
		}
		stage('Start Grid'){
			steps{
				//sh "docker-compose up -d hub chrome firefox"
				bat "docker-compose up -d hub chrome firefox"
			}
		}
		stage('Run Test'){
			steps{
				//sh "docker-compose up search-module book-flight-module"
				bat "docker-compose up search-module book-flight-module"
			}
		}
	}
	post{
		always{
			archiveArtifacts artifacts: 'output/**'
			//sh "docker-compose down"
			bat "docker-compose down"
			//sh "sudo rm -rf output/"
			bat "sudo rm -rf output/"
		}
	}
}
