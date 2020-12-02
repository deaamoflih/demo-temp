


  node { 
          stage('SCM_testing_keys_k') {
checkout([$class: 'GitSCM', branches: [[name: '*/*']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/deaamoflih/demo-temp']]])
          }
      
     
  stage('Code analysis') {
   
     def scannerHome = tool 'sonarqube';
     withSonarQubeEnv('sonarqube') { 
        sh "echo ${scannerHome}"
        sh "echo ${env.JOB_NAME}"
       sh 'printenv'
       if (env.JOB_NAME == 'demo-temp') {
         
                             sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey='develop' -Dsonar.sources='./' -Dsonar.branch=develop  " 
                        }
       else {
         sh "skipping"
       }
 
    
     }
   
  }
  
}


//-Dsonar.projectKey=${env.JOB_NAME.split('/')[0]}
//-Dsonar.projectKey=${env.JOB_NAME.split('/')[0]}
    //-Dsonar.projectName='testing' -Dsonar.projectKey='${env.JOB_NAME.split('/')[0]}' -Dsonar.sources='./' -Dsonar.branch=test_keweewys
