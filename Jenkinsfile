pipeline {
  agent {
    node {
      label 'docker'
    }

  }
  stages {
    stage('Git') {
      steps {
        git(url: 'https://github.com/panamaniantwix/flasking.git', branch: 'main')
      }
    }

    stage('Docker login') {
      steps {
        sh 'docker login -u gabriellathorne -p dckr_pat_0rgUPd4HRo0BAG3OOXoec4sR7i0 '
      }
    }

    stage('Docker Build') {
      steps {
        sh 'docker build -t gabriellathorne/flask_app .'
      }
    }

    stage('Docker Push') {
      steps {
        sh 'docker push gabriellathorne/flask_app'
      }
    }

  }
}