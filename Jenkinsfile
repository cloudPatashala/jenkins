pipeline {
    agent any
    
    parameters { choice(name: 'batch', choices: ['cp-b08', 'cp-b09', 'cp-b11'], description: '') }

    stages {
        stage('STG1') {
            steps {
               git credentialsId: 'git', url: 'git@github.com:cloudPatashala/jenkins.git'
            }
        }
        stage('STG3') {
            steps {
                echo 'This is stage 3....'
                sh 'ls -l'
            }
        }
        stage('STG2') {
            steps {
                echo 'This is Stage 2..'
                sh 'cat name.txt'
                echo "This is batch ${params.batch}"
            }
        }
		stage('Packer') {
            steps {
				sh 'packer init .'
				sh 'packer fmt .'
				sh 'packer build aws-ubuntu.pkr.hcl'
            }
        }
    }
}