pipeline {
    agent any
    stages {
        stage('0 Build') {
            steps {
                bat 'docker stop appdev'
				bat 'docker rn appdev'             
            }
        }
		stage('1 Build') {
            steps {
                bat 'docker build -t appdev .'  
				bat 'docker run -d --name test -p 8082:80 appdev'
            }
        }
    }
}