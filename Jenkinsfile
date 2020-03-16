pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            bat 'mvn compile'
          }
        }

        stage('Test') {
          steps {
            bat 'mvn test'
          }
        }

        stage('Package') {
          steps {
            bat 'mvnw package'
          }
        }

        stage('Deploy') {
          steps {
            bat 'java -jar target/*.jar'
          }
        }

      }
    }

  }
}