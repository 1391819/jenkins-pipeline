pipeline {
	agent any
	// specify environment variables
	environment {
		SECRET_KEY = credentials("SECRET_KEY")
	}
	stages {
		stage('Build') {
			steps {
				sh "sudo apt install -y python3-pip"
				sh "export SECRET_KEY=${SECRET_KEY}"
				// display current environment variables
				sh "env"
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
