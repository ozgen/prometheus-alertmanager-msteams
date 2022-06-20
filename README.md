# prometheus-alertmanager-msteams

This repository is an example of how to configure prometheus, alertmanager and prometheus-msteams for notifiying msteams channel. This repository inspired from that [blog].  
The implementation is declerative, so Helm is not used. (Only used for to generate prometheus-msteams yaml files like that `helm template prometheus-msteams/`
 ).  
## How to Setup?
1 - Create namespace monitoring : `kubectl create ns monitoring`

2 - In prometheus directory:
` kustomize build k8s | kubectl apply -f -
`
Check & port-forwarding the prometheus deployed correctly or not ? Also check rules are correctly defined or not?

3 - In nodeexporter directory:
` kustomize build k8s | kubectl apply -f -
`
Check & run this command`kubectl get pods -n monitoring` to get node-exporter up & running?

4 - In alertmanager directory: ` kustomize build k8s | kubectl apply -f -
`
Check & run this command`kubectl get pods -n monitoring` to get alertmanager up & running?

5 - In prometheus-msteams directory:

` kustomize build k8s | kubectl apply -f -
`
Check & run this command`kubectl get pods -n monitoring` to get prometheus-msteams up & running?

## To see the results :
when check the node-exporter params & configure the rule set that exceed of some params in node-exporter.
Then the results should be :

In prometheus client:

![alt tag](https://github.com/ozgen/prometheus-alertmanager-msteams/blob/main/images/prometheus.png)


In AlertManager client:

![alt tag](https://github.com/ozgen/prometheus-alertmanager-msteams/blob/main/images/alertmanager.png)


In Msteams client:

![alt tag](https://github.com/ozgen/prometheus-alertmanager-msteams/blob/main/images/msteams.png)




## Resources

https://lapee79.github.io/en/article/prometheus-alertmanager-with-msteams/
https://github.com/prometheus-msteams/prometheus-msteams/blob/master/chart/prometheus-msteams/README.md


https://www.youtube.com/watch?v=x2qTvTN8YKI

https://www.youtube.com/watch?v=bPHOI29rwB0


[blog]: https://lapee79.github.io/en/article/prometheus-alertmanager-with-msteams/
