pipeline {
  agent any
  stages {
    stage('Development Build') {
      steps {
        echo 'Pull the code from Git Repo'
      }
    }

    stage('Smoke Test') {
      steps {
        echo 'Run the Smoke Test Pack'
        echo 'Move code to QA on Smoke Test completion'
      }
    }

    stage('Integration Test') {
      parallel {
        stage('Integration Test') {
          steps {
            echo 'UI Test'
          }
        }

        stage('UI Sanity') {
          steps {
            echo 'Run UI Sanity Pack'
          }
        }

        stage('API Sanity') {
          steps {
            echo 'Run API Sanity'
          }
        }

        stage('Performance Test') {
          steps {
            echo 'Run Performance Test'
          }
        }

      }
    }

    stage('Certify the Build') {
      steps {
        echo 'Trigger Email when Build is successful'
      }
    }

  }
}