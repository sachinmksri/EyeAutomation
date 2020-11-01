pipeline {
  agent any
  stages {
    stage('Pulling code from Build') {
      steps {
        echo 'Getting code from Build/dev code'
      }
    }

    stage('Pulling Test code from Repo') {
      steps {
        git(url: 'https://github.com/sachinmksri/EyeAutomation', branch: 'master')
        bat 'mvn test -DEnvironment=QA'
      }
    }

    stage('Certification form QA') {
      steps {
        input(message: 'Are you sure to certify ', ok: 'Yes')
      }
    }

  }
}