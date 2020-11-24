node {
  stage('SCM') {
checkout([$class: 'GitSCM', branches: [[name: '*/testing_ohne_proprites']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/deaamoflih/demo-temp']]])  }
  stage('SonarQube analysis') {
      def scannerHome = tool 'sonarqube';
      withSonarQubeEnv('sonarqube') { 
        withMaven {
           def mvnHome = tool name: 'mvn', type: 'maven'
          sh "${scannerHome}/bin/sonar-scanner"
        }
 
       
  
  
    }
  }
}
