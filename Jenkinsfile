pipeline {
  agent any 
  triggers {
    pollSCM('* * * * *')
  }
  stages {
    stage("Compile") {
      steps {
        sh "mvn compile"
      }
    }
    stage("Test") {
      steps {
        sh "mvn test"
      }
    }
    stage("Compile") {
      steps {
        sh "mvn package"
      }
    }
  }
  post {
    failure {
      emailext(
        subject: "${env.JOB_NAME} [${env.BUILD_NUMBER}] Failed!",
        body: """<p>'${env.JOB_NAME} [${env.BUILD_NUMBER}]' Failed!":</p>
        <p>Check console output at &QUOT;<a href='${env.BUILD_URL}'>${env.JOB_NAME} [${env.BUILD_NUMBER}]</a>&QUOT;</p>""",
        to: "naredla.ramireddy@gmail.com"
      )
    }
  }
    
        
}
