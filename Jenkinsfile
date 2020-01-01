pipeline {
  agent {
    docker {
      args '-p 3000:3000'
      image 'httpd:2.4.41'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh '''cd /usr/local/apache2/htdocs/
ls
echo it is done'''
      }
    }

  }
}