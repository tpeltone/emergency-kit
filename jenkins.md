# Jenkins

## Useful links

[User Documentation](https://jenkins.io/doc/)

[Declarative Pipelines](https://jenkins.io/doc/book/pipeline/syntax/)

[Plugins](https://plugins.jenkins.io/)

### Swarm client

[Swarm Plugin](https://wiki.jenkins.io/display/JENKINS/Swarm+Plugin)

 ```bash
 # run this from a agent/slave to connect to the master
java -jar <path to warm-client.jar> -master <http://my.jenkins.master.net>

# ex.
java -jar swarm-client-3.17.jar -master -master http://my.jenmins.master.net:8080

 ```

 ### List installed plugins

 ```bash
# You can retrieve the information using the Jenkins Script Console which is # accessible by visiting http://<jenkins-url>/script. (Given that you are logged in and have the required permissions).

 Jenkins.instance.pluginManager.plugins.each{
  plugin -> 
    println ("${plugin.getDisplayName()} (${plugin.getShortName()}): ${plugin.getVersion()}")
}
 ```
