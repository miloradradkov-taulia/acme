CHART_REPO := gs://jenkinsxio/charts
NAME := acme
build: clean
	helm lint

clean:
	rm -rf charts
	rm -rf ${NAME}*.tgz

release: clean
	sed -i -e "s/version:.*/version: $(VERSION)/" Chart.yaml
	helm lint
	helm package .
	jx gitops helm release