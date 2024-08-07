# demo-serverless

install serverless operator

https://docs.openshift.com/serverless/1.33/install/install-serverless-operator.html

https://docs.openshift.com/serverless/1.33/install/installing-knative-serving.html

https://docs.openshift.com/serverless/1.33/install/installing-knative-eventing.html


open terminal

create project demo1

run

kn service create greeter --image quay.io/rhdevelopers/knative-tutorial-greeter:quarkus

test curl from url after run kn

create project demo2

apiVersion: serving.knative.dev/v1
kind: Service
metadata:
  name: helloworld-go
spec:
  template:
    spec:
      containers:
        - image: ghcr.io/knative/helloworld-go:latest
          env:
            - name: TARGET
              value: "Go Sample v1"

kn service update helloworld-go --env TARGET="Go Sample v2" --traffic helloworld-go-00001=50 --traffic helloworld-go-00002=50

create project demo3

deploy with image from UI

danielon30/quarkus-serverless:latest

danielon30/springboot-serverless:latest

danielon30/go-serverless:latest

danielon30/python-serverless:latest

# show in demo time

danielon30/nodejs-serverless:latest

create project demo4

install openshift pipeline

https://docs.openshift.com/serverless/1.33/functions/serverless-functions-creating.html#odc-creating-functions_serverless-functions-creating

kn func create -l node myfunc

cd myfunc

kn func deploy --remote

curl test

kn func create -l node -t cloudevents myfuncce

cd myfuncce

kn func deploy --remote

https://developers.redhat.com/blog/2021/01/04/create-your-first-serverless-function-with-red-hat-openshift-serverless-functions#example_1__create_a_serverless_function_for_http_requests

add channel all default

add eventsource, pingsource

*/1 * * * *

add link

wait until start