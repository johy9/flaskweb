pipeline {
  agent any

  stages {
    stage('Checkout SCM') {
      steps {
        git 'https://github.com/johy9/flaskapp.git' 
      }
    }

    stage('Checkout Ansible playbook') {
      steps {
        git 'https://github.com/myusername/myansibleplaybook.git'
      }
    }

    stage('Run Ansible playbook') {
      steps {
        ansiblePlaybook credentialsId: 'private-key', disableHostKeyChecking: true, installation: 'ansible-project', inventory: 'host.ini', playbook: 'test.yml'
      }
    }
  }
}
