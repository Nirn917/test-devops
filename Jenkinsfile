pipeline {
  agent {
    docker {
      image 'httpd:2.4.41'
      args '-p 3000:80'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh 'ls -l /usr/local/apache2/'
      }
    }

    stage('test') {
      steps {
        sh 'cat /usr/local/apache2/htdocs/index.html'
      }
    }

  }
}