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
              withSonarQubeEnv('sonar') {
                bat 'mvn clean package sonar:sonar'
              }
            }
          }
    }
}
