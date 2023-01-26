pipeline {
    agent any 
    environment {                                       // Declaring at pipeline will allow all the stages to access this variable
        SSH_CRED = credentials('SSH_CRED') 
    }
    stages {
        stage('Lint Checks') {
            when { branch pattern: "feature-.*", comparator: "REGEXP" }
            steps {
                sh "env"
                sh "echo runs only on feature branch"
                sh "echo lint cheks are completed."
            }
        }  

        stage('Performing a Dry-Run') {                 // Just for demo purpose we have hardcoded env and component; That can still be parameterised.
            when { branch pattern: "PR-.*", comparator: "REGEXP"}
            steps {
                sh "env"
                sh "Runs only aginst a PR"
                sh "ansible-playbook robot-dryrun.yml -e COMPONENT=frontend -e ansible_user=${SSH_CRED_USR} -e ansible_password=${SSH_CRED_PSW} -e ENV=dev"
            }
        }

        stage('Runs against Main') {
            when { branch 'main' }
            steps {
                sh "env"
                sh "echo Main Branch"
            }
        }

        stage('Runs against Tag') {
            when { expression TAG_NAME  ==~ ".*" }
            steps {
                sh "env"
                sh "echo $TAG_NAME"
            }
        }

    }
}

// Pushing changes to feature branch