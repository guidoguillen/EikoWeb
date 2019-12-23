pipeline {
    agent any
    stages {
        /*stage('0 Cleanup') {
            steps {
                bat 'docker stop test'
				bat 'docker rm test'             
            }
        }*/
		stage('1 Build') {
            steps {
                bat 'docker build -t appdev .'  
            }
        }
		stage('2 Start container and db') {
            steps {
				bat 'docker run -d --name test -p 8082:80 appdev'
				//bat 'docker exec test json-server --watch db.json --port 50255'
            }
        }
    }
}