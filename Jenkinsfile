pipeline {
  /* El agente define en que nodo se correra el pipeline */
  agent any
  stages{
    stage('Build'){
      steps {
        sh '/Users/luisrosales/Documents/apache-maven-3.5.3/bin/mvn clean package'
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
