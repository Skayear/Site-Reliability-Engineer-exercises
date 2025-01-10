APP_NAME_API=test-dev-api
APP_NAME_FRONT=test-dev-front

REGISTRY_ID=259867816695
ECR_URL=${REGISTRY_ID}.dkr.ecr.${AWS_DEFAULT_REGION}.amazonaws.com
VERSION = ${CI_PIPELINE_IID}

SERVICE_NAME_APP=Test_dev_front_11
TASK_NAME=${SERVICE_NAME_APP}:11
ECS_CLUSTER=test-dev-ecs-cluster

ecr_login:
	aws ecr get-login-password --region ${AWS_DEFAULT_REGION} | docker login --username AWS --password-stdin ${ECR_URL}
#aws ecr get-login-password --region ${AWS_DEFAULT_REGION} --registry-ids ${REGISTRY_ID} | sh

build_app_back:
	docker build -t ${ECR_URL}/${APP_NAME_API}:${VERSION} -t ${ECR_URL}/${APP_NAME_API}:latest -f ./dockerfile_net6_msb .

build_app_front:
	docker build -t ${ECR_URL}/${APP_NAME_FRONT}:${VERSION} -t ${ECR_URL}/${APP_NAME_FRONT}:latest -f ./dockerfile_front .

push_app_back: build_app_back ecr_login
	docker push ${ECR_URL}/${APP_NAME_API}:${VERSION}
	docker push ${ECR_URL}/${APP_NAME_API}:latest

push_app_front: build_app_front ecr_login
	docker push ${ECR_URL}/${APP_NAME_FRONT}:${VERSION}
	docker push ${ECR_URL}/${APP_NAME_FRONT}:latest

update_app_service:
	aws ecs update-service --cluster ${ECS_CLUSTER} --service ${SERVICE_NAME_APP} --force-new-deployment --region ${AWS_DEFAULT_REGION}
