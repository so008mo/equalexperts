#!groovy
def KEY_ID = env.AWS_ACCESS_KEY;
def ACCESS_KEY = env.AWS_SECRET_ACCESS_KEY;

pipeline {
  agent none
  stages {
    stage('Deploy') {
      agent {
        docker {
          image 'arsenal14h/eks-utils'
        }
      }
      steps {
        sh 'git clone https://github.com/so008mo/equalexperts.git'
	sh 'cp -r . /tmp/deploy'
	sh 'cd /tmp/deploy && AWS_ACCESS_KEY_ID=$KEY_ID AWS_SECRET_ACCESS_KEY=$ACCESS_KEY ansible-playbook main.yml'
      }
    }
  }
}
