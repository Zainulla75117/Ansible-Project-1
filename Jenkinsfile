pipeline {
  agent { 
  label 'ansiblenode'
  }
  
  environment {
   AWS_EC2=credentials('AWSEC2PEM') 
  }
  
  stages {
    stage('CheckOutCode'){
      steps{
        git credentialsId: '5bea97a5-1d05-46ad-bfc8-6e055e1d9ef8', url: 'https://github.com/Zainulla75117/Ansible-Project-1.git'
      }
    }
     
    stage('RunPlaybook') {
      steps {
        sh "ansible-playbook -i Inventory/project1.hosts --private-key=$AWS_EC2 Playbooks/pingServer.yaml --ssh-common-args='-o StrictHostKeyChecking=no'"
      }
    }
  
  }//stages closing
}//pipeline closing