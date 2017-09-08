pipeline {
    agent any
    stages {
        stage('build') {
            steps {
                node {
                    sh 'pwd'
                    sh 'hostname'
                    checkout scm
                    sh 'ls -la'
                    sh './pkg -l'
                }
                node {
                    sh 'hostname'
                }
            }
        }
    }
}
