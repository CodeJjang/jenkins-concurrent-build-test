pipeline {
    agent any
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage ('Build Service 1') {
            when {
                changeset "code/sample-service-1/**"
            }
            steps {
               echo 'Service 1!'
            }
        }
        stage ('Build Service 2') {
            when {
                changeset "code/sample-service-2/**"
            }
            steps {
               echo 'Service 2!'
            }
        }
        stage ('Finally') {
            steps {
               echo 'Finally!'
            }
        }
    }
}
