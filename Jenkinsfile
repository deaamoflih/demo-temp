


  node { 
          stage('SCM_testing_keys_k') {
checkout([$class: 'GitSCM', branches: [[name: '*/*']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/deaamoflih/demo-temp']]])
          }
      
     
  stage('Code analysis') {
     def scannerHome = tool 'sonarqube';
     withSonarQubeEnv('sonarqube') { 
        sh "echo ${scannerHome}"
        sh "echo ${env.JOB_NAME}"
       sh "echo ${env.BRANCH_NAME}"
 
     sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectName='t' -Dsonar.projectKey='w' -Dsonar.sources='src/' -Dsonar.language=java -Dsonar.java.binaries=* -Dsonar.branch.target=neasaw " 
     }
  }
  
}


//-Dsonar.projectKey=${env.JOB_NAME.split('/')[0]}
//-Dsonar.projectKey=${env.JOB_NAME.split('/')[0]}
    //-Dsonar.projectName='testing' -Dsonar.projectKey='${env.JOB_NAME.split('/')[0]}' -Dsonar.sources='./' -Dsonar.branch=test_keweewys
// -Dsonar.scm.disabled=true
