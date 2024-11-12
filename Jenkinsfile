pipeline{
    agent none
    stages{
        stage 'git checkout'{
            agent (label 'node1')
            steps{
                git branch: 'main',  url: 'https://github.com/sarmistha-jena/spring-petclinic.git'
            }
        }
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
}
