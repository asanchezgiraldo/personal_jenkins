# personal_jenkins
Docker base jenkins to do POCs


to get the list of plugins use the below in the script console

Jenkins.instance.pluginManager.plugins.each{
  plugin -> 
    println ("${plugin.getShortName()}:${plugin.getVersion()}")
}


to start run

docker run -p 8081:8080 -p 50001:50000 local-jenkins-2:latest
