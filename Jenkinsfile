pipeline {
  agent any
  stages {
    stage("build") {
      steps {
        echo 'Building the application using Maven...'
      }
    }
    stage("Unit and Integration Tests") {
      steps {
        echo 'Testing the application using Mocha'
      }
      post {
        success {
          emailext subject: "Test stage log",
            body: "Test stage was successful, log: Testing the application using Mocha",
            to: "benbradhurst@gmail.com",
            attachmentsPattern: '**/build.log'
        }
      }
    }
    stage("Code Analysis") {
      steps {
        echo 'Analysing the code using CheckStyle'
      }
    }
    stage("Security Scan") {
      steps {
        echo 'Security scan of application with Snyk Security'
      }
      post {
        success {
          emailext subject: "Security stage log",
            body: "Security Scan stage was successful, log: Security scan of application with Snyk Security, scan successful",
            to: "benbradhurst@gmail.com",
            attachmentsPattern: '**/build.log'
        }
      }
    }
    
    stage("Deploy to Staging") {
      steps {
        echo 'Deploying to AWS EC2 instance'
      }
    }
    stage("Integration Tests on Staging") {
      steps {
        echo 'Running integration tests on AWS EC2 environment'
      }
    }
    stage("Deploy to Production") {
      steps {
        echo 'Deploying to AWS EC2 production server'
      }
    }
  }
}
