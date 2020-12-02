


  node { 
          stage('SCM_testing_keys') {
checkout([$class: 'GitSCM', branches: [[name: '**']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/deaamoflih/demo-temp']]])
          }
      
     
  stage('Code analysis') {
     def scannerHome = tool 'sonarqube';
     withSonarQubeEnv('sonarqube') { 
        sh "echo ${scannerHome}"
        sh "echo ${env.JOB_NAME}"
       sh "echo ${env.BRANCH_NAME}"
 
     sh "${scannerHome}/bin/sonar-scanner -Dsonar.branch=develop  " 
     }
  }
  
}


//-Dsonar.projectKey=${env.JOB_NAME.split('/')[0]}
//-Dsonar.projectKey=${env.JOB_NAME.split('/')[0]}
    //-Dsonar.projectName='testing' -Dsonar.projectKey='${env.JOB_NAME.split('/')[0]}' -Dsonar.sources='./' -Dsonar.branch=test_keweewys
