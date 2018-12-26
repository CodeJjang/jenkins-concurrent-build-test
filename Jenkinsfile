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
                    agent any
                    when {
                        changeset "code/sample-service-1/**"
                    }
                    steps {
                       echo 'Service 1 sleep...'
                       sleep 20
                       echo 'Service 1!'
                    }
                }
                stage ('Build Service 2') {
                    agent any
                    when {
                        changeset "code/sample-service-2/**"
                    }
                    steps {
                       echo 'Service 2!'
                       sh 'exit 1'
                    }
                }
            }
        }
        stage ('Deploy') {
            agent any
            steps {
                echo 'Deploy!'
            }
        }
    }
}

