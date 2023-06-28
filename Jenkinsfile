/* Requires the Docker Pipeline plugin */
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
				
				checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/SurabhiKolte/BasicPrograms.git']])

				bat 'docker build -t hello_world .'

				bat 'docker run hello_world'

            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}