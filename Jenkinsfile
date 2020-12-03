

 pipeline {
    agent any
    stages {
        stage('some parallel stage') {
            parallel {
                stage('parallel stage 1') {
                    when {
                      expression { env.JOB_NAME == "demo_developooo" }
                    }
                    steps {
                        echo 'yes'
                    }
                }
                stage('parallel stage 2') {
                    steps {
                        echo 'something 2'
                    }
                }
            }
        }
    }
}
