pipeline{
	agent any
	stages {
		stage('build') {
			steps {
				echo "Running build automation"
				sh "./greadlew build --no-daemon"
				archiveArtifacts artifacts: "dist/hello.zip"
			}
		}
	}
}
