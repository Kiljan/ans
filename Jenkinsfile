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
        stage('Run ansible playbook with basic config') {
            steps {
                sh "ansible-playbook -i ${ANSPATH}/inventories/test/hosts -u vv ${ANSPATH}/test_play.yml"
            }
        }
    }
}