pipeline {
    agent any
    stages {
        stage('0 Cleanup') {
            steps {
                //bat 'docker stop test'
				//bat 'docker rm test'             
            }
        }
		stage('1 Build') {
            steps {
                bat 'docker build -t appdev .'  
            }
        }
		stage('2 Start container and db') {
            steps {
				bat 'docker run -d -p 8082:80 --name test appdev'
				bat 'docker exec -it test json-server --watch db.json --port 50255'
            }
        }
    }
}