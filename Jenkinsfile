


  node { 
          stage('SCM') {
checkout([$class: 'GitSCM', branches: [[name: '*/testing_ohne_proprites']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/deaamoflih/demo-temp']]])  }
      
      try {    
  stage('SonarQube analysis') {
     def scannerHome = tool 'sonarqube';
     withSonarQubeEnv('sonarqube') { 
        sh "echo ${scannerHome}"
        sh "echo ${env.JOB_NAME}"
       sh "echo ${env.BRANCH_NAME}"
      sh "echo ${env.JOB_NAME.split('/')[0]}"
     sh "${scannerHome}/bin/sonar-scanner -Dsonar.projectKey=${env.JOB_NAME.split('/')[0]} -Dsonar.projectName=${env.JOB_NAME.split('/')[0]} -Dsonar.sources=src/  " 
     }
  }
 }
      catch (Exception e) 
    { echo "Stage failed, but we continue"  
 } 
   stage('testing') {
sh " echo 'SUCCESS' "  }
  
}



