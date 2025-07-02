Goal is we want to generate a config file that contains:

username = ${USERNAME}
password = ${PASSWORD}

...and have it resolved to:

username = myuser
password = mysecret

...at runtime using envsubst.

In this way we can store secrets in config map which can replaced from secrets and environment variables. 

Once deployed you can verify like this 

kubectl exec -it $(kubectl get pod -l app=envsubst-demo -o jsonpath='{.items[0].metadata.name}') -- cat /output/app.conf

kubectl exec -it envsubst-demo-86c5db4f88-9v22t -n envsubst-demo -- sh

/ # cat /output/app.conf
username = myuser
password = mysecret