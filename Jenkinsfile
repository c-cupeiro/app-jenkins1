pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'BUILD'
		sh '''
            echo "Hola desde dentro"
        '''
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