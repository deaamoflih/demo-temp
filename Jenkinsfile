node {
  
  
  stage('SCM') {
    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '2678cf77-021c-4c49-a946-a53e8ac24424', url: 'https://github.com/deaamoflih/demo-temp']]])
                }
  stage('Build and Anlyzing') {
      withMaven {
        withSonarQubeEnv('sonarqube') {
        def mvnHome = tool name: 'mvn', type: 'maven' 
         def scannerHome = tool 'sonarqube';
        sh "${mvnHome}/bin/mvn package"
        sh "${mvnHome}/bin/mvn sonar:sonar -Dsonar.host.url=http://20.73.141.154:9000 -Dsonar.projectName=sfasfasf -Dsonar.projectKey=profddddissiaona -Dsonar.sources=src/main -Dsonar.tests=src/test/java"
                }
                }
  }

    
  }
