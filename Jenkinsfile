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
        stage ("build") {
            steps {
                sh 'mvn --version'
            }
        }
    }
}
