NAME = emq
VERSION_MAJOR_MINOR = 2.3
VERSION = $(VERSION_MAJOR_MINOR).4
IMAGE = labstack/$(NAME)
PREFIX = emqttd-docker
EMQTT_NAME = $(PREFIX)-v$(VERSION).zip
EMQTT_IMAGE = $(PREFIX)-v$(VERSION_MAJOR_MINOR)-$(VERSION)

build:
	wget http://emqtt.io/static/brokers/$(EMQTT_NAME)
	unzip $(EMQTT_NAME)
	docker load < $(EMQTT_IMAGE)
	docker tag $(EMQTT_IMAGE) $(IMAGE):$(VERSION)
	docker tag $(EMQTT_IMAGE) $(IMAGE):latest
	rm -rf emqttd-docker*

push: build
	docker push $(IMAGE):$(VERSION)
	docker push $(IMAGE):latest

.PHONY: build push
