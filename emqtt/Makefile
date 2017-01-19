VERSION = 2.0.6
EMQTT = emqttd-docker-v${VERSION}
LS_EMQTT = labstack/emqtt

build:
	wget http://emqtt.io/static/brokers/${EMQTT}.zip
	unzip ${EMQTT}.zip
	docker load < ${EMQTT}
	docker tag ${EMQTT} ${LS_EMQTT}:${VERSION}
	docker tag ${EMQTT} ${LS_EMQTT}:latest
	rm -rf emqttd-docker*

push: build
	docker push labstack/emqtt

.PHONY: build push
