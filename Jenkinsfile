 node { 


            stage('para') {
                parallel {
                    stage('one') {
                        steps {
                            script {
                               sh "echo 'one' "
                            }
                        }
                    }
                    stage('two') {
                        steps {
                            script {
                                sh "echo 'two' "
                                }
                            }
                        }
                    }
                }
            }
