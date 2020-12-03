

 pipeline {
    agent any
    stages {
        stage('some parallel stage') {
            parallel {
                stage('parallel stage 1') {
                    when {
                      expression { ENV == "something" }
                    }
                    steps {
                        echo 'something'
                    }
                }
                stage('parallel stage 2') {
                    steps {
                        echo 'something'
                    }
                }
            }
        }
    }
}
