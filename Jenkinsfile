pipeline {
    agent any
    tools{
        maven 'maven'
    }
    stages{
        stage('Build Maven'){
            steps{
                checkout([$class: 'GitSCM', branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/krishnarayapudi25/hello-world-maven-application-Jenkins-CI-CD-pipeline-.git']]])
                sh 'mvn clean install'
            }
        }
        stage('Build Docker images'){
            steps{
                sh 'docker build -t krishnaim:latest .'
            }
        }
        stage('push Docker image'){
            steps{
                sh 'docker login -u 'Username' -p 'password'

                sh 'docker tag krishnaim krishnarayapudi25/krishnaim'


                sh 'docker push krishnarayapudi25/krishnaim:latest'
            }
        }
    }
}