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
          sh "${scannerHome}/bin/sonar-scanner -D sonar.projectKey=pro -D sonar.projectName=what -D sonar.sources=src/main"
        }
 
       
  
  
    }
  }
}
