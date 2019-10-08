pipeline {
    agent any
    tools{
	maven 'Maven 3.6.2'
	}
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
		sh 'mvn clean compile'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
		sh 'mvn test'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
		sh 'mvn -DskipTests package'
		archiveArtifacts artifacts: '**/target/*.jar', fingerprint: true
            }
        }
    }
}

