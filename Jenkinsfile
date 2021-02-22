pipeline {
    agent any
    tools{
        maven 'Maven'
        jdk 'JDK'

    }
    
    stages {
                stage('build && SonarQube analysis') {
            steps {
                withSonarQubeEnv('sonar') {
                    // Optionally use a Maven environment you've configured already
                        bat 'mvn clean package sonar:sonar'
                    
                }
            }
        }

        stage('Test') { 
            steps {
                bat 'mvn test' 
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml' 
                }
            }
        }
    }
}
