pipeline {
	agent any
	stages {
		stage('Build') {
			steps {
				sh "sudo apt install -y python3-pip"
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
