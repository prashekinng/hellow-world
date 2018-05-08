pipeline {
agent any 
stages {
   stage ('compile stage') {
   steps {
    sh 'mvn compile'
    }
   }
   stage ('test stage') {
   steps {
   sh 'mvn test'
     }
   }
   stage ('package') {
   steps {
      sh 'mvn package'
      }
   }
 }
 post {
   always {
     archiveArtifacts artifacts: 'pom$BUILD_NUMBER.xml',  fingerprint: true
   
     }
   }
}
