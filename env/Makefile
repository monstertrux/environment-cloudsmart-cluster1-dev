init:
	helm init --client-only --stable-repo-url https://charts.helm.sh/stable
	helm repo add jenkins-x https://storage.googleapis.com/chartmuseum.jenkins-x.io
	helm repo add storage.googleapis.com https://storage.googleapis.com/chartmuseum.jenkins-x.io
	helm repo add bitnami https://charts.bitnami.com/bitnami
	helm repo add stable https://charts.helm.sh/stable

build: clean init
	jx step helm build --boot --provider-values-dir=../kubeProviders
	helm lint .

clean: 
	rm -rf charts
	rm -rf requirements.lock
