pipeline {
  agent any
  stages {
    stage('compile') {
      steps {
        echo 'this is the compile job'
        sh 'npm install'
        sleep 4
      }
    }

    stage('test') {
      steps {
        echo 'this is the test job'
        sh 'npm test'
        sleep 9
      }
    }

    stage('package') {
      steps {
        echo 'this is the package job'
        sh 'npm run package'
        echo 'Will sleep for 7'
        sleep 7
      }
    }

    stage('archive') {
      steps {
        archiveArtifacts '**/distribution/*.zip'
      }
    }

  }
  tools {
    nodejs 'nodejs'
  }
  post {
    always {
      echo 'this pipeline has completed...'
    }

  }
}