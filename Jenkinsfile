node {
  stage('SCM') {
checkout([$class: 'GitSCM', branches: [[name: '*/testing_ohne_proprites']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/deaamoflih/demo-temp']]])  }
  stage('SonarQube analysis') {
      def scannerHome = tool 'sonarqube';
      withSonarQubeEnv('sonarqube') { // If you have configured more than one global server connection, you can specify its name
 
       sh "${scannerHome}/bin/sonar-scanner"
  
  
    }
  }
}
