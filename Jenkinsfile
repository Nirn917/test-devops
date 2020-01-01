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
        sh '''cp -f ./index.html /usr/local/apache2/htdocs/index2.html
echo it is done'''
      }
    }

  }
}