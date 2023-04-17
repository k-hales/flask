pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('git') {
      steps {
        git(url: 'https://github.com/k-hales/flask', branch: 'main')
      }
    }

    stage('build') {
      steps {
        sh 'docker build -t khales7/flask_app .'
      }
    }

    stage('docker login') {
      steps {
        sh 'docker login -u khales7 -p dckr_pat_yv-6kKwy4T974w-pV79IWDq_fKA'
      }
    }

    stage('docker push') {
      steps {
        sh 'docker push khales7/flask_app'
      }
    }

  }
}