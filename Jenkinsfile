pipeline {
    agent any
    stages {
        stage('0 Cleanup') {
            steps {
                bat 'docker stop test'
				bat 'docker rm test'             
            }
        }
		stage('1 Build') {
            steps {
                bat 'docker build -t appdev .'  
				bat 'docker run -d --network host --name test appdev'
				bat 'json-server --watch db.json --port 50255'
            }
        }
		stage('2 Start container and db') {
            steps {
				bat 'docker run -d --network host --name test appdev'
				bat 'json-server --watch db.json --port 50255'
            }
        }
    }
}