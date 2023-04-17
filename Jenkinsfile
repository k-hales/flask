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
        sh 'docker build -t k-hales/flask_app .'
      }
    }

    stage('docker login') {
      steps {
        sh 'docker login -u k-hales -p dckr_pat_yv-6kKwy4T974w-pV79IWDq_fKA'
      }
    }

    stage('docker push') {
      steps {
        sh 'docker push k-hales/flask_app'
      }
    }

  }
}