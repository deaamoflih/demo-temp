node {
  
  
  stage('SCM') {
    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '2678cf77-021c-4c49-a946-a53e8ac24424', url: 'https://github.com/deaamoflih/demo-temp']]])
                }
  stage('Build') {
      withMaven {  
        def mvnHome = tool name: 'mvn', type: 'maven' 
        sh "${mvnHome}/bin/mvn package"
                }
                }
  stage ('SonarQube analysis') {
    def scannerHome = tool 'sonarqube';
    withSonarQubeEnv('sonarqube') {
      sh "mvn sonar:sonar -Dsonar.host.url=http://20.73.141.154:9000"
    }
  }
  }
