pipeline { 
  agent { label 'master' } 
  environment {
    SPECTRAL_DSN = credentials('spectral-dsn')
  }
  stages {
    stage('install Spectral') {
      steps {
        sh "curl -L 'https://bruce-mountain-16192.herokuapp.com/latest/x/sh?dsn=$SPECTRAL_DSN' | sh" 
      }
    }
    stage('scan for issues') {
      steps {
        sh "$HOME/.spectral/spectral scan" 
      }
    }
  }
}
