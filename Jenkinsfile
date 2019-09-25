pipeline {
  agent any
  parameters {
    string(name: 'FETCHER_NAME', description: 'Name of targetted fetcher to deploy.')
    string(name: 'FETCHER_VERSION', description: 'Version at time of build used for reporting.')
    choice(name: 'DEPLOY_ENVIRONMENT', choices: ['dev', 'prod'], description: 'The environment in which to deploy fetchers to.')
  }

  stages {
    stage('Pushed tags') {
      when { buildingTag() }
      steps {
        echo "!!! Pushed tags...."
        echo "$ENV"
      }
    }

    stage ('Dev build') {
      when { branch 'dev' }
      steps {
        echo "!!! Dev build...."
        echo "$ENV"
      }
    }

    stage ('prod build') {
      when { branch 'prod' }
      steps {
        echo "!!! Prod build...."
        echo "$ENV"
      }
    }

    
  }
}
