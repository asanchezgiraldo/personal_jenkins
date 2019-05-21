# personal_jenkins
Docker base jenkins to do POCs

## To get the list of plugins use the below in the script console from an existing Jenkins server

- [ ] Go to Menu

![Jenkins Menu](/resources/jenkins_menu.jpg)


- [ ] Select Screen console option

![Script console options](/resources/script_console_opt.jpg)


- [ ] Run Script

```
Jenkins.instance.pluginManager.plugins.each{
  plugin -> 
    println ("${plugin.getShortName()}:${plugin.getVersion()}")
}
```
![Script and output](/resources/script_and_output.jpg)


- [ ] Copy list on plugin.txt file in the root folder

## To build image from Dockerfile (this includes the plugins from plugins.txt

  ```
  docker build -t <jenkins-image-name> --no-cache --force-rm=true .
  ```

## To start run

  ```
  docker run -p 8081:8080 -p 50000:50000 <jenkins-image-name>:latest
  ```
  
- [ ] Enter Admin password
![Enter Admin Password](/resources/admin_password.jpg)


- [ ] Install suggested Plugins

- [ ] Create User
![Enter Admin Password](/resources/create_user.jpg)


  
## Copy existing jobs

  ```
  docker cp OLD_CONTAINERID:/var/jenkins_home/jobs export_jobs
  docker cp export_jobs/* NEW_CONTAINERID:/var/jenkins_home/jobs
  ```
  Then got to jenkins and reload config, this migth not work if you need to migrate some credentials
  
    
