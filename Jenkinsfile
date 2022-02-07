pipeline {
  agent any
  stages {
    stage('test') {
      parallel {
        stage('test') {
          steps {
            echo 'step1'
            sh 'echo "halo" >> test.txt'
          }
        }

        stage('staging') {
          steps {
            sleep 10
          }
        }

      }
    }

    stage('test2') {
      steps {
        dir(path: '/var/www/html/') {
          sh 'git pull'
          sh 'git commit '
          dir(path: '/var/www/html/jenkins/')
        }

      }
    }

  }
}