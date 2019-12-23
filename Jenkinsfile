pipeline {
    agent any
    stages {
        stage('0 Build') {
            steps {
                sh 'docker stop appdev'
				sh 'docker rn appdev'             
            }
        }
		stage('1 Build') {
            steps {
                sh 'docker build -t appdev .'  
				sh 'docker run -d --name test -p 8082:80 appdev'
            }
        }
    }
}