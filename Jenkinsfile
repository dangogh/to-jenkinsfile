pipeline {
    agent { docker 'node:6.3' }
    stages {
        stage('build') {
            steps {
                sh 'pwd'
                sh 'id'

                checkout scm
                sh './pkg -l'
            }
        }
    }
}
