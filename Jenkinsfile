pipeline {
    agent any

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

        stage('Post-build Cleanup') {
            steps {
                deleteDir()
            }
        }
    }

}