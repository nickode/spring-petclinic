pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        catchError(buildResult: 'mvn compile') {
          mail(subject: 'Error: Unable to build project spring-petclinic', body: 'Was not able to build.', to: 'nicolasnsamaha@hotmail.com', from: 'nicolasnsamaha@hotmail.com')
          echo 'Build failed.'
        }

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
        bat 'git add .'
        bat 'git commit -m "Commit"'
        bat 'git push'
      }
    }

  }
}