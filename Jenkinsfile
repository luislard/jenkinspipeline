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
          archiveArtifacts artifacts: '**/target/*.war'
        }
      }
    }
    stage('Deploy to Staging'){
      steps {
        /* Build job defined in Jenkins */
        /* One benefit on doing this wasy is that the devOps Engineer */
        /* Will not need access to development repo and this file to  */
        /* change the IP address or the hosts names of the server that */
        /* this job gets deployed to */
        build job: 'Deploy-to-staging'
      }
    }
  }
}
