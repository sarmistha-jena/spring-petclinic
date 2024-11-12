pipeline{
    agent any
    stages{
        stage('git checkout'){
            //agent (label 'demo1')
            steps{
                git branch: 'main',  url: 'https://github.com/sarmistha-jena/spring-petclinic.git'
            }
        }
        stage('Maven Install') {
            //agent (label 'demo1')
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
