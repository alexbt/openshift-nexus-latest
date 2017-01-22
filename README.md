With this project, you can easily deploy the **latest** Nexus Repository to your OpenShift Online account.

#Forked
This repository was forked this project from **https://github.com/juliogonzalez/sonatype-nexus-openshift**, which was configured (at the time) for *v3
.1.0-04*.

**It was modified so that it always (dynamically) uses the version.**

#How to Deploy
Using `Openshift 2` command line tool (`rhc`), type the following command to deploy:
> rhc app-create nexus diy-0.1 --from-code https://github.com/alexbt/openshift-nexus-latest.git

The process will take some time (accessing the url will display a *503*), you may connect to the server and tail 
the logs:

> ssh 588fef487628e10cd10000f0@$APPNAME-$USER.rhcloud.com
>
> tail -f $OPENSHIFT_DATA_DIR/log/nexus.log
  
