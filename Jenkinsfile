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
        sh '''cd /usr/local/apache2/htdocs/
ls
curl http://127.0.0.1/index.html
echo it is done'''
      }
    }

  }
}