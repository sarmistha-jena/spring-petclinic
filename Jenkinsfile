pipeline{
    agent { label 'demo1'}
    stages{
        stage('Maven Install') {
            agent {
                docker {
                    image 'maven:3.5.0'
                }
            }
            steps {
                sh 'mvn clean install'
            }
        }
        stage('Docker Build') {
            agent any
            steps {
                sh 'docker build -t sarmisthajena/spring-petclinic:latest .'
            }
        }
    }
}
