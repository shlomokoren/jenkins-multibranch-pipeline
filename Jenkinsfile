properties([buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '', daysToKeepStr: '', numToKeepStr: '7')),
 parameters([string(defaultValue: 'bitnami', description: '', name: 'repoName', trim: false), 
            string(defaultValue: 'https://charts.bitnami.com/bitnami', description: '', name: 'repoUrl', trim: false), 
			string(defaultValue: 'joomla', description: '', name: 'release', trim: false), 
			string(defaultValue: 'bitnami/joomla', description: '', name: 'chart', trim: false)])])
node('jenkins-jenkins-slave '){
    stage('helm tests'){
        sh label: '', script: '''
         curl https://get.helm.sh/helm-v2.16.5-linux-amd64.tar.gz -o helm-v2.16.5-linux-amd64.tar.gz
         ls
         tar -zxvf helm-v2.16.5-linux-amd64.tar.gz
         chmod +x linux-amd64/helm
         curl -LO https://storage.googleapis.com/kubernetes-release/release/v1.18.0/bin/linux/amd64/kubectl
		 chmod +x ./kubectl
		 ./kubectl version
         ./kubectl config set-context --current --namespace=jenkins	 
         linux-amd64/helm version
         echo end'''
        
    }
}