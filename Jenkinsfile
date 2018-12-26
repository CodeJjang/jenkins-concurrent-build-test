pipeline {
    agent any
    options { disableConcurrentBuilds() }
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage ('Build services') {
            parallel {
                stage ('Build Service 1') {
                    steps {
                       echo 'Service 1 sleep...'
                       sleep time:10, unit: SECONDS
                       echo 'Service 1!'
                    }
                }
                stage ('Build Service 2') {
                    steps {
                       echo 'Service 2!'
                       sh 'exit 1'
                    }
                }
            }
        }
        stage ('Deploy') {
            steps {
                echo 'Deploy!'
            }
        }
    }
}

