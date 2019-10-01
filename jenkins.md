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
# You can retrieve the information using the Jenkins Script Console which is accessible by visiting http://<jenkins-url>/script. (Given that you are logged in and have the required permissions).

# unsorted list
 Jenkins.instance.pluginManager.plugins.each{
  plugin -> println ("${plugin.getDisplayName()} (${plugin.getShortName()}): ${plugin.getVersion()}")
}

# sorted list
jenkins.model.Jenkins.instance.getPluginManager().getPlugins().stream().sorted().each { println "${it.getShortName()} | ${it.getVersion()} | ${it.getDisplayName()}" }


#Worked well for me on Mac OS X. I wanted to convert the output to a plain text list, so used some Perl regex to strip the tags
curl 'http://192.168.197.133:8080/pluginManager/api/xml?depth=1&xpath=/*/*/shortName|/*/*/version&wrapper=plugins' | perl -pe 's/.*?<shortName>([\w-]+).*?<version>([^<]+)()(<\/\w+>)+/\1 \2\n/g'

 ```
