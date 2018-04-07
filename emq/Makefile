NAME = emq
VERSION = 2.3.6
IMAGE = labstack/$(NAME)
EMQTT = emqttd-docker-v$(VERSION)

build:
	wget http://emqtt.io/static/brokers/$(EMQTT).zip
	unzip $(EMQTT).zip
	docker load < $(EMQTT)
	docker tag $(EMQTT) $(IMAGE):$(VERSION)
	docker tag $(EMQTT) $(IMAGE):latest
	rm -rf emqttd-docker*

push: build
	docker push $(IMAGE):$(VERSION)
	docker push $(IMAGE):latest

.PHONY: build push