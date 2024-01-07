pipeline {
  agent any
  stages {
    stage('git pull') {
      steps {
        // https://github.com/akm4545/k8s-GitOps-study.git will replace by sed command before RUN
        git url: 'https://github.com/akm4545/k8s-GitOps-study.git', branch: 'main'
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