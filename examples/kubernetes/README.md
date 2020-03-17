# Install guide for kubernetes

This guide will deploy jitsi in the most simple way: as several containers in a single pod. This is enough to start in case your hardware is enough. If you need to scale components to severa instance, you'll have to modify it to use several services and pods.

Create a namespace to deploy jitsi to:

`kubectl create namespace jitsi`

Add the secret with secret values (replace `...` with some random strings):

`kubectl create secret generic jitsi-config --from-literal=JICOFO_COMPONENT_SECRET=`openssl rand -base64 18` --from-literal=JICOFO_AUTH_PASSWORD=`openssl rand -base64 18` --from-literal=JVB_AUTH_PASSWORD=`openssl rand -base64 18`

`k apply -k .`