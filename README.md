# personal_jenkins
Docker base jenkins to do POCs

## To build this image run

  ```
  docker build -t jenkins-image-name --no-cache --force-rm=true .
  ```


## To get the list of plugins use the below in the script console

Jenkins.instance.pluginManager.plugins.each{
  plugin -> 
    println ("${plugin.getShortName()}:${plugin.getVersion()}")
}


## To start run

  ```
  docker run -p 8081:8080 -p 50001:50000 ljenkins-image-name:latest
  ```