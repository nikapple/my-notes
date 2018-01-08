
# Logs from client

 @ INFO @  @ Before @ com.readingmonitor.controller.LoginController @ processLogin @ 26141343860141  
 @ INFO @  @ Before @ com.readingmonitor.service.UserServiceImpl @ validateUser @ 26141350858591  
 @ INFO @  @ Before @ com.readingmonitor.dao.UserDaoImpl @ validateUser @ 26141351281318  
 @ INFO @  @ After @ com.readingmonitor.dao.UserDaoImpl @ validateUser @ 26141468683780  
 @ INFO @  @ After @ com.readingmonitor.service.UserServiceImpl @ validateUser @ 26141469261506  
 @ INFO @  @ Before @ com.readingmonitor.service.UserServiceImpl @ getUserInfo @ 26141511389914
 @ INFO @  @ Before @ com.readingmonitor.dao.UserDaoImpl @ getUserInfo @ 26141511934752  
 @ INFO @  @ After @ com.readingmonitor.dao.UserDaoImpl @ getUserInfo @ 26141514548791  
 @ INFO @  @ After @ com.readingmonitor.service.UserServiceImpl @ getUserInfo @ 26141514960268  
 @ INFO @  @ After @ com.readingmonitor.controller.LoginController @ processLogin @ 26141516174063  


##### Logs from dynamodb



Before 26141343860141 com.readingmonitor.controller.LoginController com.readingmonitor.controller.LoginController processLogin  
Before 26141350858591 com.readingmonitor.controller.LoginController com.readingmonitor.service.UserServiceImpl validateUser  
Before 26141351281318 com.readingmonitor.service.UserServiceImpl com.readingmonitor.dao.UserDaoImpl validateUser  
After 26141468683780 com.readingmonitor.dao.UserDaoImpl com.readingmonitor.dao.UserDaoImpl validateUser  
After 26141469261506 com.readingmonitor.dao.UserDaoImpl com.readingmonitor.service.UserServiceImpl validateUser  
<span style="color:yellow">Before 26141511389914 com.readingmonitor.service.UserServiceImpl com.readingmonitor.service.UserServiceImpl getUserInfo</span>  
Before 26141511934752 com.readingmonitor.service.UserServiceImpl com.readingmonitor.dao.UserDaoImpl getUserInfo  
After 26141514548791 com.readingmonitor.dao.UserDaoImpl com.readingmonitor.dao.UserDaoImpl getUserInfo  
After 26141514960268 com.readingmonitor.dao.UserDaoImpl com.readingmonitor.service.UserServiceImpl getUserInfo  
After 26141516174063 com.readingmonitor.service.UserServiceImpl com.readingmonitor.controller.LoginController processLogin  

PLANT UML
************

@startuml

autonumber

   participant "com.readingmonitor.dao.UserDaoImpl"
   participant "com.readingmonitor.service.UserServiceImpl"
   participant "com.readingmonitor.controller.LoginController"


		 	activate "com.readingmonitor.controller.LoginController"
	 	"com.readingmonitor.controller.LoginController" ->>  "com.readingmonitor.controller.LoginController" : processLogin
	 		 	activate "com.readingmonitor.service.UserServiceImpl"
	 	"com.readingmonitor.controller.LoginController" ->>  "com.readingmonitor.service.UserServiceImpl" : validateUser
	 		 	activate "com.readingmonitor.dao.UserDaoImpl"
	 	"com.readingmonitor.service.UserServiceImpl" ->>  "com.readingmonitor.dao.UserDaoImpl" : validateUser
	 			 "com.readingmonitor.dao.UserDaoImpl" ->>  "com.readingmonitor.dao.UserDaoImpl" : validateUser
	  	deactivate "com.readingmonitor.dao.UserDaoImpl"
	 				 	activate "com.readingmonitor.dao.UserDaoImpl"
	 	"com.readingmonitor.service.UserServiceImpl" ->>  "com.readingmonitor.dao.UserDaoImpl" : getUserInfo
	 			 "com.readingmonitor.dao.UserDaoImpl" ->>  "com.readingmonitor.dao.UserDaoImpl" : getUserInfo
	  	deactivate "com.readingmonitor.dao.UserDaoImpl"
	 				 "com.readingmonitor.service.UserServiceImpl" ->>  "com.readingmonitor.controller.LoginController" : processLogin
	  	deactivate "com.readingmonitor.service.UserServiceImpl"

@enduml
... (skipping 14 lines) ...
	 	"com.readingmonitor.service.UserServiceImpl" ->>  "com.readingmonitor.dao.UserDaoImpl" : validateUser
	 			 "com.readingmonitor.dao.UserDaoImpl" ->>  "com.readingmonitor.dao.UserDaoImpl" : validateUser
	  	deactivate "com.readingmonitor.dao.UserDaoImpl"
	 				 	activate "com.readingmonitor.dao.UserDaoImpl"
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
 Activate/Deactivate already done on com.readingmonitor.dao.UserDaoImpl
