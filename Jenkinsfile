pipeline{

agent any

stages{

stage('Clone a repo')
{
    steps{

        git branch: 'main', url: 'https://github.com/Sonal0409/CEP-1-Ansible-Jenkins-Abhay.git'
 }

}

stage('Playbook to Install Maven & Docker')
{
   steps{

ansiblePlaybook credentialsId: 'ansible_credentials', disableHostKeyChecking: true, installation: 'myansible', inventory: 'dev.inv', playbook: 'playbookInstall.yml'

}

}

stage('plabook to build and deploy java app on docker container')

{

steps{

ansiblePlaybook credentialsId: 'ansible_credentials', disableHostKeyChecking: true, installation: 'myansible', inventory: 'dev.inv', playbook: 'playbookDeployment.yml'

}

}

}

}







