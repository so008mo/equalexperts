def KEY_ID = env.AWS_ACCESS_KEY;
def ACCESS_KEY = env.AWS_SECRET_ACCESS_KEY;

stage('deploy') {
 node('master') {

     docker.image('arsenal14h/eks-utils').inside("-u 0") {
	   sh "rm -rf equalexperts && git clone https://github.com/so008mo/equalexperts.git"
	   sh 'cd equalexperts && AWS_ACCESS_KEY_ID=$KEY_ID AWS_SECRET_ACCESS_KEY=$ACCESS_KEY ansible-playbook main.yml'
	   }
	   }
	   }
