# Multi_Module_Maven_Project
Simple Multi Module Maven Project with packaging as ear 
-->How to create this project in eclipse
Step1: (to create main maven project)(project: auctionsystem) file-->new-->maven project
        a. Tick the checkbox create simple project(skip archtype selection) and click next
        b. Enter groupId, artifactId and version
        c. select packaging as pom
        d. click finish
Step2: (project: inventory/ordermanager)right click on main maven project, new-->other-->maven module
      Note: If you want to create simple java project Tick the checkbox 
      create simple project(skip archtype selection) and click next, if not uncheck it. Here I want to create web application 
      so I wont tick the checkbox
        a. Enter module name
        b. Under filter search as "webapp"--> select webapp artifact and click next
        c. In next step groupId, artifactId and version will take automatically, just click finish.
        d. modify pom.xml and add if you have any dependencies
Step3: follow similar steps, if you need to create few more modules under main maven project

Note: Now we have 1 main maven project with packaging as pom and 2 separate j2ee web application maven modules.
      To package application as ear, follow below steps
      
Step4: file-->new-->maven project(project: auctionsystem-ear)
        a. Tick the checkbox create simple project(skip archtype selection) and click next
        b. Enter groupId, artifactId and version
        c. select packaging as jar/war(later in pom.xml we need to change this to ear)
        d. click finish     
Step5: Open pom.xml of above project and change packaging to ear and also add other module dependencies(refer to pom
under project created in step4(project: auctionsystem-ear))
        a. under src\main add "application\META-INF" directory.
        b. under META-INF, add "weblogic-application.xml" file(already present in project)
--------------------------------------------------------------------------------------------------------------------
Step6: Update maven project
        a. right click on main maven project-->maven-->update project--> click select all-->tick force upate of snapshot
        option in the below
        b. press ok
Step7: Build maven project
        a. right click on main maven project-->run as--> maven install
----------------------------------------------------------------------------------------------------------------------------
ear file will generated under auctionsystem-->auctionsystem-ear-->target
Eg: auctionsystem-ear-0.0.1-SNAPSHOT.ear

Step8: If you have running tomEE plus server, just copy this file under webapps folder and access it through any browser.

Note: URL's to particular module you will find under same target folder, file name will be application.xml
        
