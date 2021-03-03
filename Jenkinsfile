pipeline {
    agent any
	
    triggers {
        pollSCM '* * * * *'
    }

    stages {
        stage('stage1') {
            steps {
                echo 'Test1'
		sh 'echo Test2'
		sh 'ls -a'
		sh 'pwd'
            }
        }
	stage('stage2') {
            steps {
                script {
                    if (env.BRANCH_NAME == 'master') {
                        echo 'I execute on the master branch'
                    } else {
                        echo 'I execute elsewhere'
                    }
                }
            }
        }
	stage('stage3') {
            steps {
                sh 'chmod +x testscript.sh'
		sh 'testscript.sh'
            }
        }
    }
}


