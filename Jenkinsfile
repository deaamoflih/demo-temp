


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
     sh "${scannerHome}/bin/sonar-scanner -D sonar.projectKey=${env.JOB_NAME.split('/')[0]} -D sonar.projectName=${env.JOB_NAME.split('/')[0]} -D sonar.sources=src/  -D sonar.host.url=http://localhost:8080/ " 
     }
  }
 }
      catch (Exception e) 
    { echo "Stage failed, but we continue"  
 } 
   stage('testing') {
sh "SUCCESS"  }
  
}


//### -D sonar.host.url=127.0.0.1:9000
