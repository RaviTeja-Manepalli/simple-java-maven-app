pipeline{
   agent any
   tools{
      maven 'Maven'
        jdk 'JDK'
   }
  stages {
          stage("build & SonarQube analysis") {
            agent any
            steps {
              withSonarQubeEnv('sonarcloud') {
                bat 'java -version'
                bat 'mvn clean package sonar:sonar'
              }
            }
          }
    }
}
