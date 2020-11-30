


  node { 
          stage('SCM_testing_keys') {
checkout([$class: 'GitSCM', branches: [[name: '*/test_keys']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/deaamoflih/demo-temp']]])
          }
      
     
  stage('Code analysis') {
     def scannerHome = tool 'sonarqube';
     withSonarQubeEnv('sonarqube') { 
        sh "echo ${scannerHome}"
        sh "echo ${env.JOB_NAME}"
       sh "echo ${env.BRANCH_NAME}"
      sh "echo ${env.JOB_NAME.split('/')[0]}"
       sh "echo ${env.JOB_NAME.split('/')[1]}"
     sh "${scannerHome}/bin/sonar-scanner  -Dsonar.projectName=${env.JOB_NAME.split('/')[0]} -Dsonar.sources=src/   " 
     }
  }
  
}


//-Dsonar.projectKey=${env.JOB_NAME.split('/')[0]}
//-Dsonar.projectKey=${env.JOB_NAME.split('/')[0]}
