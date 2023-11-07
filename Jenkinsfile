pipeline {
    agent { 
        node { 
            label 'terra' 
            } 
        }

    environment {
        ANSPATH = '/home/vv/ansible'
    }

    stages {
        stage('Remove known_hosts') {
            steps {
                sh "rm -rf /home/vv/.ssh/known_hosts"
            }
        }

        stage('Run ansible playbook with basic config') {
            steps {
                dir ("${ANSPATH}") {
                    sh "ansible-playbook -i ${ANSPATH}/inventories/test/hosts -u vv ${ANSPATH}/test_play.yml"
                }
            }
        }
    }
}