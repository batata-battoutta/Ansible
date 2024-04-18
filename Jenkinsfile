pipeline {
    agent {
        docker {
            image 'ansible/ansible:latest'
            args '-v /var/run/docker.sock:/var/run/docker.sock'  // Mount Docker socket for Docker inside Docker
        }
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/batata-battoutta/Ansible.git'
            }
        }

        stage('Run Ansible Playbook') {
            steps {
                script {
                    // Specify the path to your Ansible playbook YAML file
                    def playbookPath = "DeployMyProject.yml"

                    // Run the Ansible playbook
                    sh "ansible-playbook $playbookPath"
                }
            }
        }

        
    }

}