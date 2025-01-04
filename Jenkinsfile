pipeline {
    agent any

    tools {
        maven 'Maven 3.9.6'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
                sh  'mvn clean install'
            }
        }
        stage('Test') {
            steps {
                echo 'Deploying the project...'
                sh 'mvn clean test'
            }
        }
        stage('Package') {
            steps {
                echo 'Testing the project...'
                sh 'mvn package -DskipTests'
            }
        }



            
        }

          post {
        success {
            archiveArtifacts artifacts: '**/target/*.jar', allowEmptyArchive: true
        }
    }

    }
