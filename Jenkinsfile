pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('git') {
      steps {
        git(url: 'https://github.com/edwinomella/flasking', branch: 'main')
      }
    }

    stage('build') {
      steps {
        sh 'docker build -t edwinomella/flask_app .'
      }
    }

    stage('docker login') {
      steps {
        sh 'docker login -u edwinoneal -p dckr_pat_F9ZBav6fbv_IRcRVic_iGJRIRbc'
      }
    }

    stage('docker push') {
      steps {
        sh 'docker push edwinomella/flask_app'
      }
    }

  }
}