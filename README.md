# XWiki Helm Chart

This is the XWiki [Helm Chart](https://helm.sh/) aiming to ease the deployment in both Local and Highly Available setups.  


## Resources

* XWiki Installation Guide: https://www.xwiki.org/xwiki/bin/view/Documentation/AdminGuide/Installation
* XWiki Docker : https://github.com/xwiki-contrib/docker-xwiki


## Prerequisite

* Minikube
* Kubectl cli
* helm cli

## Installation on Minikube

* First, enable ingress

```bash
minikube addons enable ingress
```

* Install chart

```bash
cd xwiki-helm
helm dependency update
helm --debug upgrade -i --force xwiki -f ./values.yaml .
```

## Usage

```bash
kubectl port-forward svc/xwiki-xwiki 80
```
URL: `http://localhost`

## Test

For testing first add [unittest](https://github.com/lrills/helm-unittest#install)
```bash
helm plugin install https://github.com/lrills/helm-unittest
helm unittest xwiki-helm
```

## Project Information

* Project Lead: [Ashish Sharma](https://www.xwiki.org/xwiki/bin/view/XWiki/ashish932)
* [Issue Tracker](http://jira.xwiki.org/browse/HELM)
* Communication: [Mailing List](http://dev.xwiki.org/xwiki/bin/view/Community/MailingLists), [IRC](http://dev.xwiki.org/xwiki/bin/view/Community/IRC)
* [Development Practices](http://dev.xwiki.org)
* Minimal XWiki version supported: XWiki 8.4
* License: LGPL 2.1
* Translations: N/A
* Sonar Dashboard: N/A
* Continuous Integration Status: N/A
