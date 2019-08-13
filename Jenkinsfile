pipeline {
  agent any
  tools {
    maven 'Maven 3.5.4'
  }
  stages {
    stage ('env') {
        sh 'printenv'
    }
    stage ('Compile') {
      steps {
        sh 'mvn compile'
      }
    }
  }
  post {
    success { gerritReview score:1, message:'It works' }
    failure { gerritReview score:-1, message:'Breaks the build' }
  }
}
