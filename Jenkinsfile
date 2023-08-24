pipeline {
	agent any
	// specify environment variables
	environment {
		SECRET_KEY = credentials("SECRET_KEY")
		DOCKER_LOGIN = credentials("DOCKER_LOGIN")
	}
	stages {
		stage('Build') {
			steps {
				sh "sudo apt install -y python3-pip"
				sh "export SECRET_KEY=${SECRET_KEY}"
				// display current environment variables
				sh "env"
				// docker is not installed on the current VM
				// but if it was, we'd enable the following 
				//sh "docker login -u ${DOCKER_LOGIN_USR} -p ${DOCKER_LOGIN_PSW}"
			}
        	}
        	stage('Dependencies') {
            		steps {
                		sh "pip install -r requirements.txt"
            		}
        	}
        	stage('Deploy') {
            		steps {
                		sh "python3 app.py"
            		}
        	}
    	}
}
