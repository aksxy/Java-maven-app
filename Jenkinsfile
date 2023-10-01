pipeline {
	agent any
	parameters {
		choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: 'Select the version to deploy to prod')
		booleanParam(name: 'executeTests', defaultValue: true, description: 'Run tests during deployment')
	}
	environment {
		// Remove unused environment variables
		// NEW_VERSION = '1.3.0'
		// SERVER_CREDENTIALS = credentials('Server-Credentials')
	}
	stages {
		stage("build") {
			steps {
				echo 'Building the application..!'
			}
		}
		stage("test") {
			when {
				expression {
					params.executeTests
				}
			}
			steps {
				echo 'Testing the application..!'
			}
		}
		stage("deploy") {
			steps {
				echo 'Deploying the application...'
				
				// If you intend to use credentials, uncomment and configure this section
				// withCredentials([
				//	usernamePassword(credentials: 'Server-Credentials', usernameVariable: 'USER', passwordVariable: 'PWD')
				// ]) {
				//	sh "some script ${USER} ${PWD}"
				// }
				
				// Use correct variable name for VERSION
				echo "Deploying version ${params.VERSION}"
			}
		}
	}
}
