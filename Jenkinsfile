pipeline {
  /* El agente define en que nodo se correra el pipeline */
  agent any
  stages{
    stage('Build'){
      steps {
        mvn clean package
      }
      post {
        success {
          echo 'Now Archiving...'
          archiveArtifacts artifacts: '**target/*.war'
        }
      }
    }
  }
}
