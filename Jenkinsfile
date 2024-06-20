pipeline {
    agent any
    tools {
        maven 'maven'
    }
    stages {
        stage ("checkout") {
            steps {
                git branch: 'main', credentialsId: '19534d8c-d99d-432d-a6c9-56219e094828', url: 'https://github.com/codepipe/k-s-n-v-g.git'
            }
        }
        stage ("version-check") {
            steps {
                sh 'mvn --version'
            }
        }
        stage ("build") {
            steps {
                sh 'mvn install'
            }
        }
        stage ("deploy") {
            steps {
                deploy adapters: [tomcat9(credentialsId: '6ec55b9b-21fa-46b4-9901-ec4d7f4b16ac', path: '', url: 'http://65.2.9.77:8080/')], contextPath: null, war: '**/*.war'
            }
        }   
    }
}
