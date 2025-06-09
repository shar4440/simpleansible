pipeline{
  agent any

  tools{
    maven 'Maven'
  }
  environment{
    LANG= "en_US.UTF-8"
    LC_ALL= "en_US.UTF-8"
  }

  stages{
    stage('checkout'){
      steps{
        git branch: 'master', url: 'https://github.com/shar4440/simpleansible.git'
      }
    }

    stage('build'){
      steps{
        sh 'mvn clean package'
      }
    }

    stage('run'){
      steps{
        sh 'mvn clean package'
        sh 'ansible-playbook ansible/playbook.yml -i ansible/hosts.ini'
      }
    }
  }
  
}
