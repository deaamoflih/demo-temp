pipeline {
    agent none
  stage("Parallel") {
    steps {
        parallel (
            "firstTask" : {
                sh "echo ss"
            },
            "secondTask" : {
                sh "echo ssssss"
            }
        )
    }
}
}
