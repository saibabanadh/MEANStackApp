node {
  stage('SCM') {
    checkout poll: false, scm: [$class: 'GitSCM', branches: [[name: 'refs/heads/develop']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/saibabanadh/MEANStackApp.git']]]
  }
  stage('SonarQube Analysis') {
        def scannerHome = tool 'SonarScanner 4.0';
        sh "${scannerHome}/bin/sonar-scanner -Dsonar.host.url=http://sonarqube:9000 -Dsonar.projectName=meanstackapp -Dsonar.projectVersion=1.0 -Dsonar.projectKey=meanstack:app -Dsonar.sources=. -Dsonar.projectBaseDir=/home/jenkins/workspace/mean-pipeline"
    }
  }
