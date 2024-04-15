pipeline {
    agent {
        docker {
            image 'ansible/ansible:lts'
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
                    def playbookPath = "docker_start.yml"

                    // Run the Ansible playbook
                    sh "ansible-playbook $playbookPath"
                }
            }
        }

        
    }

}