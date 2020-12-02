


  node { 
          stage('SCM_testing_keys_k') {
            steps {
              parallel (
                para1 : {
                  echo "jooo"
                  sleep 10
                };
                para2 : {
checkout([$class: 'GitSCM', branches: [[name: '*/*']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/deaamoflih/demo-temp']]])
          };
                }      
          }
      
     
  stage('Code analysis') {
   
     def scannerHome = tool 'sonarqube';
     withSonarQubeEnv('sonarqube') { 
        sh "echo ${scannerHome}"
        sh "echo ${env.JOB_NAME}"
       sh 'printenv'
       if (env.JOB_NAME == 'demo_develop') {
         
                             sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey='develop' -Dsonar.sources='./' -Dsonar.branch=develop  " 
                        }
       else {
         sh "echo 'skipping' "
       }
 
    
     }
   
  }
  
}


//-Dsonar.projectKey=${env.JOB_NAME.split('/')[0]}
//-Dsonar.projectKey=${env.JOB_NAME.split('/')[0]}
    //-Dsonar.projectName='testing' -Dsonar.projectKey='${env.JOB_NAME.split('/')[0]}' -Dsonar.sources='./' -Dsonar.branch=test_keweewys
