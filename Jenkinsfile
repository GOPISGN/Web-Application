pipeline {
	agent any
     
	stages {
			
		stage('Stage 1 : Pre-check Python is installed or not') {
			steps {
				bat 'echo "Check Python Version"'
				bat 'python --version'
				bat 'echo "Python latest version is installed, up and running"'
			}
		}
		
		stage('Stage 2 : Lauching a web application') {
			parallel {
				stage('Invoke HTTP Server') {
					steps {
						bat 'echo "Invoke HTTP Server"'
						bat 'python -m http.server'
					}
				}
				stage('Open browser via localhost') {
					steps {
						bat 'echo "Open google chrome and launch index.html page"'
						bat 'start chrome http://localhost:8000/index.html'
					}
				}
			}
		}
		
	}
}
