node {
  stage('Clone the Git') {
    git 'https://github.com/SonarSource/sonar-scanning-examples.git'
  }
  stage('SonarQube analysis') {
    def scannerHome = tool 'sq1';
    withSonarQubeEnv('sq1') {
      sh "${scannerHome}/bin/sonar-scanner \
      -D sonar.login=admin \
      -D sonar.password=Laptop@786 \
      -D sonar.projectKey=sonarqubetest1 \
      -D sonar.exclusions=vendor/**,resources/**,**/*.java \
      -D sonar.host.url=http://192.168.12.93:9000"
    }
  }
}
