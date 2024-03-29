########################
## Globals
########################
DOCKER_IMAGE_REPOSITORY :=
BUILD_FROM := builder:alpine_a64_3.14.2

##############################
## All
##############################
.PHONY: all
all: build-bats build-cookiecutter build-google-cloud build-hadolint build-hashicorp build-kubectl build-shellcheck build-terraform-docs build-kics build-tflint

########################
## Bats
########################
BATS_VERSION := 0.4.0
BATS_SUPPORT_VERSION := 0.3.0
BATS_ASSERT_VERSION := 2.0.0
BATS_MOCK_VERSION := 1.0.1
BATS_BUILD_NAME := bats
BATS_BUILD_TAG := 0.4.0alpine3.14.2

.PHONY: build-bats
build-bats:
	docker build --no-cache \
		--build-arg IMAGE=${BUILD_FROM} \
		--build-arg BATS_VERSION=${BATS_VERSION} \
		--build-arg BATS_SUPPORT_VERSION=${BATS_SUPPORT_VERSION} \
		--build-arg BATS_ASSERT_VERSION=${BATS_ASSERT_VERSION} \
		--build-arg BATS_MOCK_VERSION=${BATS_MOCK_VERSION} \
		-t ${BATS_BUILD_NAME}:${BATS_BUILD_TAG} \
		-f bats/Dockerfile .


########################
## Cookiecutter
########################
COOKIECUTTER_BUILD_FROM := python:3.9.5alpine3.14.2
COOKIECUTTER_VERSION := 1.7.3
COOKIECUTTER_BUILD_NAME := cookiecutter
COOKIECUTTER_BUILD_TAG := 1.7.3alpine3.14.2

.PHONY: build-cookiecutter
build-cookiecutter:
	docker build --no-cache \
		--build-arg IMAGE=${COOKIECUTTER_BUILD_FROM} \
		--build-arg COOKIECUTTER_VERSION=${COOKIECUTTER_VERSION} \
		-t ${COOKIECUTTER_BUILD_NAME}:${COOKIECUTTER_BUILD_TAG} \
		-f cookiecutter/Dockerfile .



########################
## Google Cloud
########################
GOOGLE_CLOUD_BUILD_FROM := google/cloud-sdk:353.0.0-alpine
GOOGLE_CLOUD_BUILD_NAME := googlecloud
GOOGLE_CLOUD_TAG := 353.0.0alpine3.14.2

.PHONY: build-google-cloud
build-google-cloud:
	docker build --no-cache \
		--build-arg IMAGE=${GOOGLE_CLOUD_BUILD_FROM} \
		-t ${GOOGLE_CLOUD_BUILD_NAME}:${GOOGLE_CLOUD_TAG} \
		-f google-cloud/Dockerfile .

########################
## Hadolint
########################
HADOLINT_BUILD_NAME := hadolint
HADOLINT_VERSION := 1.15.0
HADOLINT_BUILD_TAG := 1.15.0alpine3.14.2

.PHONY: build-hadolint
build-hadolint:
	docker build --no-cache \
		--build-arg IMAGE=${BUILD_FROM} \
		--build-arg HADOLINT_VERSION=${HADOLINT_VERSION} \
		-t ${HADOLINT_BUILD_NAME}:${HADOLINT_BUILD_TAG} \
		-f hadolint/Dockerfile .

########################
## Hashicorp
########################
HASHICORP_BUILD_FROM := sethvargo/hashicorp-installer:0.2.0
HASHICORP_BUILD_NAME := hashicorp
HASHICORP_BUILD_TAG := 0.2.0alpine3.14.2
TERRAFORM_V12 := 0.12.31
TERRAFORM_V13 := 0.13.7
TERRAFORM_V14 := 0.14.11
TERRAFORM_V15 := 0.15.5
TERRAFORM_V1	:= 1.1.0
PACKER_VERSION := 1.7.4
VAULT_VERSION := 1.8.2

.PHONY: build-hashicorp
build-hashicorp:
	docker build --no-cache \
		--build-arg IMAGE=${HASHICORP_BUILD_FROM} \
		--build-arg TERRAFORM_V12=${TERRAFORM_V12} \
		--build-arg TERRAFORM_V13=${TERRAFORM_V13} \
		--build-arg TERRAFORM_V14=${TERRAFORM_V14} \
		--build-arg TERRAFORM_V15=${TERRAFORM_V15} \
		--build-arg TERRAFORM_V1=${TERRAFORM_V1} \
		--build-arg PACKER_VERSION=${PACKER_VERSION} \
		--build-arg VAULT_VERSION=${VAULT_VERSION} \
		-t ${HASHICORP_BUILD_NAME}:${HASHICORP_BUILD_TAG} \
		-f hashicorp/Dockerfile .

########################
## Kics
########################
KICS_BUILD_NAME := kics
KICS_VERSION := 1.4.5
KICS_BUILD_TAG := 1.4.5alpine3.14.2

.PHONY: build-kics
build-kics:
	docker build --no-cache \
		--build-arg IMAGE=${BUILD_FROM} \
		--build-arg KICS_VERSION=${KICS_VERSION} \
		-t ${KICS_BUILD_NAME}:${KICS_BUILD_TAG} \
		-f kics/Dockerfile .


########################
## Kubectl
########################
KUBECTL_BUILD_NAME := kubectl
KUBECTL_BUILD_TAG := 1.15.12alpine3.14.2
KUBECTL_VERSION := 1.15.12

.PHONY: build-kubectl
build-kubectl:
	docker build --no-cache \
		--build-arg IMAGE=${BUILD_FROM} \
		--build-arg KUBECTL_VERSION=${KUBECTL_VERSION} \
		-t ${KUBECTL_BUILD_NAME}:${KUBECTL_BUILD_TAG} \
		-f kubectl/Dockerfile .

########################
## Shellcheck
########################
SHELLCHECK_BUILD_NAME := shellcheck
SHELLCHECK_BUILD_TAG := 0.6.0alpine3.14.2
SHELLCHECK_VERSION := 0.6.0

.PHONY: build-shellcheck
build-shellcheck:
	docker build --no-cache \
		--build-arg IMAGE=${BUILD_FROM} \
		--build-arg SHELLCHECK_VERSION=${SHELLCHECK_VERSION} \
		-t ${SHELLCHECK_BUILD_NAME}:${SHELLCHECK_BUILD_TAG} \
		-f shellcheck/Dockerfile .

########################
## TFlint
########################
TFLINT_BUILD_NAME := tflint
TFLINT_BUILD_TAG := 0.34.1alpine3.14.2
TFLINT_VERSION := 0.34.1

.PHONY: build-tflint
build-tflint:
	docker build --no-cache \
		--build-arg IMAGE=${BUILD_FROM} \
		--build-arg TFLINT_VERSION=${TFLINT_VERSION} \
		-t ${TFLINT_BUILD_NAME}:${TFLINT_BUILD_TAG} \
		-f tflint/Dockerfile .


########################
## Terraform Docs
########################
TERRAFORM_DOCS_BUILD_NAME := terraform-docs
TERRAFORM_DOCS_BUILD_TAG := 0.15.0alpine3.14.2
TERRAFORM_DOCS_VERSION := 0.15.0

.PHONY: build-terraform-docs
build-terraform-docs:
	docker build --no-cache \
		--build-arg IMAGE=${BUILD_FROM} \
		--build-arg TERRAFORM_DOCS_VERSION=${TERRAFORM_DOCS_VERSION} \
		-t ${TERRAFORM_DOCS_BUILD_NAME}:${TERRAFORM_DOCS_BUILD_TAG} \
		-f terraform-docs/Dockerfile .
