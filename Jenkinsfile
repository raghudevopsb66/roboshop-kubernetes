node() {
  ansiColor('xterm') {
    stage('CheckOut Code') {
      sh 'find . | sed 1d | xargs rm -rf'
      git branch: 'main', url: "https://github.com/raghudevopsb66/roboshop-kubernetes"
    }


    stage('Create Cluster') {
      sh '''
pwd
        cd infra
        pwd
        ls
        terrafile
        terraform init -backend-config env/prod-backend.tfvars
        terraform apply -var-file env/prod.tfvars
      '''
    }
  }
}
