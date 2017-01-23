With this project, you can easily deploy the **latest** Nexus Repository to your OpenShift Online account.

#Forked
This repository was forked this project from **https://github.com/juliogonzalez/sonatype-nexus-openshift**, which was configured (at the time) for *v3
.1.0-04*.

**It was then modified so that it always (dynamically) uses the latest version.**

The installation uses the following link to download the latest version: http://download.sonatype.com/nexus/3/latest-unix.tar.gz

#How to Deploy
Using `Openshift 2` command line tool (`rhc`), type the following command to deploy:

    rhc app-create nexus diy-0.1 --from-code https://github.com/alexbt/openshift-nexus-latest.git

The process will take some time (the deployment takes somewhere around 5-10 minutes!). If you try accessing the application too quickly, it may display the following message:

> Service Temporarily Unavailable
> 
> The server is temporarily unable to service your request due to maintenance downtime or capacity problems. Please try again > later.

If that is the case, you may connect to the server and tail 
the logs to see what is going on:

    ssh 588fef487628e10cd10000f0@$APPNAME-$USER.rhcloud.com
    tail -f $OPENSHIFT_DATA_DIR/data/log/nexus.log
  
