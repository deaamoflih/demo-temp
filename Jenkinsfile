


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
       sh "printenv"
       def BRANCH = sh(returnStdout: true, script: 'git rev-parse --abbrev-ref HEAD').trim()
       sh "echo ${BRANCH}"
 
     sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectName='${env.JOB_NAME}' -Dsonar.projectKey='${env.JOB_NAME}' -Dsonar.sources='src/' -Dsonar.language=java  -Dsonar.branch='/branch-mastro' " 
     }
  }
  
}


//-Dsonar.projectKey=${env.JOB_NAME.split('/')[0]}
//-Dsonar.projectKey=${env.JOB_NAME.split('/')[0]}
    //-Dsonar.projectName='testing' -Dsonar.projectKey='${env.JOB_NAME.split('/')[0]}' -Dsonar.sources='./' -Dsonar.branch=test_keweewys
// -Dsonar.scm.disabled=true
