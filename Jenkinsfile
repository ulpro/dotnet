pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'dotnet Build eShopOnWeb.sln'
      }
    }

    stage('Test') {
      parallel {
        stage('unit') {
          steps {
            sh 'dotnet test tests/UnitTests'
          }
        }

        stage('integration') {
          steps {
            sh 'dotnet test tests/IntegrationTests'
          }
        }

        stage('functionel') {
          steps {
            sh 'dotnet test tests/FunctionalTests'
          }
        }

      }
    }

    stage('Deploiement') {
      steps {
        sh 'dotnet publish eShopOnWeb.sln  C:\\Users\\tankoua\\Desktop\\ecole\\aspnet'
      }
    }

  }
}