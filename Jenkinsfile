pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // github.com/jinKim1 will replace by sed command before RUN
        git url: 'github.com/jinKim1', branch: 'main'
      }
    }
    stage('k8s deploy'){
      steps {
        kubernetesDeploy(kubeconfigId: 'kubeconfig',
                         configs: '*.yaml')
      }
    }    
  }
}