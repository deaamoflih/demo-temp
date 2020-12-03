


  node { 
          stage('SCM_testing_keys_kpppp') {
            steps {

checkout([$class: 'GitSCM', branches: [[name: '*/*']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/deaamoflih/demo-temp']]])
          }
          }
                     
          
      
     
  stage('Code analysis') {
     def scannerHome = tool 'sonarqube';
     withSonarQubeEnv('sonarqube') { 
        sh "echo ${scannerHome}"
        sh "echo ${env.JOB_NAME}"
       sh 'printenv'
       when {
           expression { 
               return env.JOB_NAME == 'demo_develop'; }
       }
       steps {
         
                             sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey='develop' -Dsonar.sources='./' -Dsonar.branch=develop  " 
                        }
 
    
     }
   
  }
  
}



