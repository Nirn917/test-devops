pipeline {
  agent {
    docker {
      args '-u root:root -p 3000:80'
      image 'ubuntu:xenial'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh '''apt update
apt install -y apache2 nodejs npm
/etc/init.d/apache2 start
cp ./index.html /var/www/html/

'''
      }
    }

    stage('test') {
      agent any
      steps {
        sh 'cat /var/www/html/index.html'
      }
    }

  }
}