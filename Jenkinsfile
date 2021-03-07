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
		echo "env.JOB_NAME = ${env.JOB_NAME}"
		echo "env.NODE_NAME = ${env.NODE_NAME}"
		sh "echo \$LANGUAGE"
		sh "printenv"
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
		sh 'sh testscript.sh'
            }
        }
    }
}


