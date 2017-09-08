#!groovy

node('docker') {
    currentBuild.result = "SUCCESS"

    try {
        stage('Checkout') {
            checkout scm
        }

        stage('Build') {
            sh 'ls -l'
                sh './pkg -v traffic_ops_build'
        }

        stage('Test TrafficOps') {
            sh 'docker-compose -p t -f traffic_ops/app/bin/tests/docker-compose.yml up --build unit'
        }

       stage('Cleanup'){
            sh 'docker-compose -p t -f traffic_ops/app/bin/tests/docker-compose.yml down -v'
       }
    }
    catch (err) {

        currentBuild.result = "FAILURE"
/*
            mail body: "project build error is here: ${env.BUILD_URL}" ,
            from: 'xxxx@yyyy.com',
            replyTo: 'yyyy@yyyy.com',
            subject: 'project build failed',
            to: 'zzzz@yyyyy.com'
*/
        throw err
    }

}
