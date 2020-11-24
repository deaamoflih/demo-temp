node {
  stage('SCM') {
checkout([$class: 'GitSCM', branches: [[name: '*/testing_ohne_proprites']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/deaamoflih/demo-temp']]])  }
  stage('SonarQube analysis') {
      def scannerHome = tool 'sonarqube';
      withSonarQubeEnv('sonarqube') { 
        withMaven {
           def mvnHome = tool name: 'mvn', type: 'maven'
          sh "echo ${scannerHome}"
          sh "echo ${env.JOB_NAME}"
          sh "echo ${env.BRANCH_NAME}"
          sh "echo ${env.JOB_NAME.split('/')[0]}"
          sh "${scannerHome}/bin/sonar-scanner -D sonar.projectKey=${env.JOB_NAME.split('/')[0]} -D sonar.projectName=${env.JOB_NAME.split('/')[0]} -D sonar.sources=src/ "
        }
 
       
  
  
    }
  }
}
