# Sample application for OpenShift 3

This sample application will create and deploy a Java EE application server as well as a MongoDB database.  The sample application will display a map and perform geospatial queries to populate the map with some French Wines locations and personal hilarious reviews (I was tired, sorry for that).

There are two options for this sample application depending on what you have available in your environment.  The options are to use JBoss EAP latest or Wildfly latest.  If you are using the openshift all-in-one image, use Wildfly.  If you are using OpenShift Online 3, Dedicated, or Enteprise, use EAP.

## Quick instructions to just get this working on an OpenShift 3 deployment as a normal user

````
$ oc login https://yourOpenShiftServer
$ oc new-project mlbparks
````
If your environment (all-in-one) has Wildfly, use this:
`````
$ oc create -f https://raw.githubusercontent.com/alexlovesgithub/openshift3mlbparks/master/mlbparks-template-wildfly.json
$ oc new-app mlbparks-wildfly
`````
If your environment (Online 3, Dedicated, OSE) has EAP, use this:
`````
$ oc create -f https://raw.githubusercontent.com/alexlovesgithub/openshift3mlbparks/master/mlbparks-template-eap.json
$ oc new-app mlbparks-eap
`````


## Install template as cluster-admin for everyone to use

Load the template with cluster-admin user:

````
# oc create -f https://raw.githubusercontent.com/alexlovesgithub/openshift3mlbparks/master/mlbparks-template-wildfly.json -n openshift
````


This application is a fork from Neale's one (https://github.com/nealef/openshift3mlbparks), which is a fork from 
Grant Shipley repository (https://github.com/gshipley/openshift3mlbparks).

Feel free to contact me if you'd like to talk about changes I've made.
