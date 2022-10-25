node() {
  ansiColor('xterm') {
    stage('CheckOut Code') {
      sh 'find . | sed 1d | xargs rm -rf'
      git branch: 'main', url: "https://github.com/raghudevopsb66/roboshop-kubernetes"
    }


    stage('Create Cluster') {
      sh '''
        cd infra
        terrafile
        terraform init -backend-config env/prod-backend.tfvars
        terraform apply -auto-approve -var-file env/prod.tfvars
      '''
    }
  }
}
