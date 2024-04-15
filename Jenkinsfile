pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/batata-battoutta/Ansible.git'
            }
        }

        stage('Run Ansible Playbook') {
            agent{
                docker {
                    image 'ansible/ansible:lts'
                }
            }
            steps {
                script {
                    // Specify the path to your Ansible playbook YAML file
                    def playbookPath = "docker_start.yml"

                    // Run the Ansible playbook
                    sh "ansible-playbook $playbookPath"
                }
            }
        }

        
    }

}