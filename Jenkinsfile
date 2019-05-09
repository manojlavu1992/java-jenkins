pipeline{
  agent any

  // options{
  //   buildDiscarder(logRotator(numToKeepStr: '2', artifactNumToKeepStr: '1'))  //keeps only 2 build
  // }

  stages{
    stage('build') {
      steps{
        sh 'ant -f build.xml -v'
      }
    }
  }

  post {
    always {
      archiveArtifacts artifacts: 'dist/*.jar', fingerprint: true
    }
  }
}