pipeline{
	agent any

	stages {
		stage ('Compile Stage') {
			withMaven(maven :'M3') {
				sh 'mvn clean compile'
			}
		}
	}

	stages {
		stage ('Testing Stage') {
			withMaven(maven :'M3') {
				sh 'mvn test'
			}
		}
	}

	stages {
		stage ('Deployment Stage') {
			withMaven(maven :'M3') {
				sh 'mvn deploy'
			}
		}
	}
}
