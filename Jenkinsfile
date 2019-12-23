pipeline {
    agent any
    stages {
        
		stage('1 Build') {
            steps {
                bat 'docker build -t appdev .'  
				bat 'docker run -d --name test -p 8082:80 appdev'
            }
        }
    }
}