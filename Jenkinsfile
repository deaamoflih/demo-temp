pipeline {
  stages {
    stage("Work 1"){
     steps{
      parallel ( "Build common Library":   
            {
              node('<Label>'){
                  sh "echo ss"
                  }
            },

        "Build Utilities" : {
            node('<Label>'){
               sh "echo ssss"
              }
           }
         )
    }
}
