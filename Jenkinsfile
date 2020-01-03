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
apt install -y apache2 curl net-tools
/etc/init.d/apache2 start
cp ./index.html /var/www/html/

'''
      }
    }

    stage('Pre-check') {
      steps {
        sh '''cat /var/www/html/index.html
netstat -taupen
ip a
'''
      }
    }

    stage('Test') {
      steps {
        sh 'curl 127.0.0.1'
      }
    }

  }
}