pipeline {
	agent any
	parameters{
		//string(name: 'VERSION', defaultValue: '', description: 'version to deploy on prod')
		choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: '')
		booleanParam(name: 'executeTests', defaultValue: true, description: '')
	environment {
		//NEW_VERSION = '1.3.0'
		//SERVER_CREDENTIALS = credentials('Server-Credentials')
	}
	stages {
		stage("build") {
			steps {
			echo 'building the application..!'
			
			}
		}
		stage("test") {
			when {
				expression {
					params.executeTests
				}
			}
			steps {
				echo 'testing the application..!'
			}
		}
		stage("deploy") {
			steps{
				echo 'deplying the application...'
				//withCredentials([
			//	usernamePassword(credentials: 'Server-Credentials', usernameVariable: USER, passwordVariavle: PWD) 
			//	]) {
				//	sh "some script ${USER} ${PWD}"  
			       // }
			       echo "deploying version $params.VERSION}"
			}
		}	
}

