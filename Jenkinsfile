pipeline {
    agent any
    stages {
        stage('0 Build') {
            steps {
                bat 'docker stop test'
				bat 'docker rm test'             
            }
        }
		stage('1 Build') {
            steps {
                bat 'docker build -t appdev .'  
				bat 'docker run -d --name test -p 8082:80 -p 80:50255 appdev'
            }
        }
    }
}