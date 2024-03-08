pipeline {
    agent any
    
    parameters { choice(name: 'batch', choices: ['cp-b08', 'cp-b09', 'cp-b11'], description: '') }

    stages {
        stage('STG1') {
            steps {
               git url: 'https://github.com/cloudPatashala/jenkins.git'
            }
        }
        stage('STG3') {
            steps {
                echo 'This is stage 3....'
                sh 'ls -l'
				sleep 13
            }
        }
        stage('STG2') {
            steps {
                echo 'This is Stage 2..'
                sh 'cat name.txt'
				sleep 10
                echo "This is batch ${params.batch}"
            }
        }
		stage('STG4') {
            steps {
				echo "nothing much to do with jenkins"
            }
        }
    }
}
