pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'docker build -t app .'
      }
    }
    post {
        always{
            echo "Esto siempre saldrá por pantalla"
        }
        failure{
            echo "Hay un error en el stage"
        }
        unstable {
            echo "ESto es si hay inestabilidad"
        }
        success{
            echo "Esto sale si ha ido bien"
        }
    }
    stage('Test') {
      steps {
        echo 'TEST'
      }
    }
	stage('Deploy') {
      steps {
        echo 'DEPLOY'
      }
    }
    post {
        always(dir) {
            cleanWS
        }
    }
  }
}