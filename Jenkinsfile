pipeline {
	agent none
	stages {
		stage('test') {
			steps {
				script {
					echo "Testing the application.."
					//echo "Executing pipeline for branch $BRANCH_NAME"
				}
			}
		}
		stage('build') {
			// when {
			// 	expression {
			// 		BRANCH_NAME == 'main'
			// 	}
			// }
			steps {
				script {
					echo "Building the application.."
					echo 'hi I am akshay...! and trying to auto building the application..?'
					echo 'check the auto push and build work or not'
				}
			}
		}
		stage('deploy') {
			// when {
			// 	expression {
			// 		BRANCH_NAME == 'main'
			// 	}
			// }
			steps {
				script {
					echo "Deploying the application.."
				}
			}
		}
	}
}
