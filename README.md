#What is this
With this project, you can easily deploy the latest Nexus Repository to your OpenShift Online account.

#Forked from juliogonzalez
I forked this project from **https://github.com/juliogonzalez/sonatype-nexus-openshift**, which was configured for 3
.1.0-04. I modified it to dynamically fetch & deploy the **latest** version.

#How to Deploy
using Openshift 2 command line tool, type:
> rhc app-create nexus diy-0.1 --from-code https://github.com/alexbt/sonatype-nexus-openshift.git

The process will take some time (accessing the url will display a 503), you may connect to the server and tail 
the logs:

> ssh 588fef487628e10cd10000f0@$APPNAME-$USER.rhcloud.com
> tail -f $OPENSHIFT_DATA_DIR/log/nexus.log
  