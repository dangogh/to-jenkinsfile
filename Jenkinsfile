pipeline {
    agent { docker 'node:6.3' }
    stages {
        stage('build') {
            steps {
                checkout scm
                sh './pkg -l'
            }
        }
    }
}
