node {
  stage('SCM') {
    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '2678cf77-021c-4c49-a946-a53e8ac24424', url: 'https://github.com/deaamoflih/demo-temp']]])
  }
  stage('SonarQube analysis') {
      def scannerHome = tool 'sonarqube';
      withSonarQubeEnv('sonarqube') { // If you have configured more than one global server connection, you can specify its name
 
       sh "${scannerHome}/bin/sonar-scanner"
  
  
    }
  }
}
