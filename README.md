# Deploy Redis to Kubernetes

`kinflate inflate -f . | kubectl apply -f -`

## Check that the redis pod has started successfully

`kubectl get pods`

Should show a pod named:

`redis-<random-bits>`

Next look at the logs:



`kubectl logs <pod-name>`

The last line of the log should say:

`1:M 07 Feb 19:22:03.760 * Ready to accept connections`

Now connect to the pod to run the Redis command line tool:

`kubectl exec -it <pod-name> -- redis-cli`

Should see command line prompt:

`127.0.0.1:6379>`

Type in the following:

`ping`

which should return:

`PONG`

Type the following on the prompt:

`set mykey somevalue`

which should return:

`OK`

Type the following on the prompt:

`get mykey`

which should return:

`¨somevalue¨`
