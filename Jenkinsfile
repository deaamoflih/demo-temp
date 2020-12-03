pipeline {
    agent none
    stages {
        stage('Run Tests') {
            parallel {
                stage('Test On Windows') {
                    agent {
                        label "windows"
                    }
                    steps {
                        sh "echo s "
                    }
                    post {
                        always {
                            sh "echo TEST-*.xml"
                        }
                    }
                }
                stage('Test On Linux') {
                    agent {
                        label "linux"
                    }
                    steps {
                        sh "echo xx"
                    }
                    post {
                        always {
                            sh "echo ss"
                        }
                    }
                }
            }
        }
    }
}
