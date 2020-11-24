node {
  stage('SCM') {
    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/deaamoflih/demo-temp']]])
  }
  stage('SonarQube analysis') {
      def scannerHome = tool 'sonarqube';
      withSonarQubeEnv('sonarqube') { // If you have configured more than one global server connection, you can specify its name
        sh "echo ${env.SONAR_HOST_URL}"
        sh "echo ${env.SONAR_CONFIG_NAME}"
        sh "printenv"
       sh "${scannerHome}/bin/sonar-scanner"
  
  
    }
  }
}
