pipeline {
  agent any
  stages {
    stage('Git Check Out') {
      steps {
        git(url: 'https://github.com/oralabuser/PipelineScript.git', branch: 'main')
      }
    }

    stage('Build') {
      steps {
        sh 'bash Build.sh'
      }
    }

    stage('Deploy') {
      steps {
        sh 'bash Deploy.sh'
      }
    }

    stage('Quality') {
      steps {
        sh 'bash Quality.sh'
      }
    }

  }
}