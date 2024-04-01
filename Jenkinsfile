pipeline {
    agent { label 'jenkins-agent'}
    tools {
        jdk 'java17'
        maven 'Maven3'
    }
    stage("cleanup workspace"){
            steps {
            cleanws ()
            }
    }
    stage("Checkout from SCM"){
            steps {
            git branch: 'main' , CredentialsId: 'github' , url: 'https://github.com/AWS-Trainees-Practice/NEW_APP_PROJECT.git'
            }
    }
    stage("Build Application"){
        stage {
            sh "mvn clean package"
        }
    }
    stage("Test Application")
        steps {
              sh "mvn test"
        }
    }
  }
}
