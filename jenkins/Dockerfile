FROM jenkins/jenkins:lts

USER root
RUN apt-get update && apt-get install -y \
	docker.io \
	docker-compose \
	&& rm -rf /var/lib/apt/lists/*

RUN jenkins-plugin-cli --plugins \
	configuration-as-code:1734.vb_70478c1b_25a_ \
	workflow-aggregator \
	git \
	docker-workflow

COPY casc.yml /var/jenkins_home/casc.yaml

ENV CASC_JENKINS_CONFIG=/var/jenkins_home/casc.yaml

USER jenkins
