pipeline {
  agent any
  stages {
    stage('Init') {
      steps {
        sh 'cd /terraform'
        sh 'terraform init'
      }
    }
    stage('Plan') {
      steps {
        sh 'terraform plan'
      }
    }
    stage('Validate Apply') {
      input {
        message "Do you want to apply this plan?"
        ok "Apply plan"
      }
    steps {
        echo 'Apply Accepted'
      }
    }
    stage('Apply') {
      steps {
        sh 'terraform apply -auto-approve'
      }
    }
  }
}
 