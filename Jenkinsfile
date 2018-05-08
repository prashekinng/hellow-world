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
   stage ('package') {
   steps {
      sh 'mvn package'
      }
   }
   stage ('Docker Build') {
   steps {
      sh 'docker build -t hello-world . '
      }
   }
 }
 
}
