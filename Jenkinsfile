/* Requires the Docker Pipeline plugin */
pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
				
				checkout scmGit(branches: [[name: '*/master']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/SurabhiKolte/CppDemo.git']])
				
				bat "\"${tool 'MSBuild'}\" CppDemo.sln /p:Configuration=Release /p:Platform=\"Any CPU\"
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