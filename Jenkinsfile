pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // github.com/jinKim1 will replace by sed command before RUN
        git url: 'https://github.com/jinKim1/gitOps.git', branch: 'main'
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
