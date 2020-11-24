# 74cms Remote Code Execution Vulnerability
* Vulnerability Type :  
Remote Code Execution  
* Vulnerability Version :  
74CMS < 6.0.48  
* Recurring environment:  
Windows 10  
PHP 5.4.5  
Apache 2.4.23
* Vulnerability analysis  
Vulnerability file:in /Application/Common/Controller/BaseController.class.php used assign_resume_tpl method.    
![image](https://github.com/BigTiger2020/74CMS/blob/main/01.png)

in /ThinkPHP/Library/Think/View.class.php   
![image](https://github.com/BigTiger2020/74CMS/blob/main/02.png)  

To view a profile: /ThinkPHP/Conf/convention.php  
![image](https://github.com/BigTiger2020/74CMS/blob/main/03.png)   

The think template is enabled  
![image](https://github.com/BigTiger2020/74CMS/blob/main/04.png)   

follow-up file: /ThinkPHP/Library/Think/Hook.class.php  
![image](https://github.com/BigTiger2020/74CMS/blob/main/05.png)  

Hook configuration file: /ThinkPHP/Mode/common.php  
![image](https://github.com/BigTiger2020/74CMS/blob/main/06.png)   

It depends on the implementation of run method,in /ThinkPHP/Library/Behavior/ParseTemplateBehavior.class.php  
![image](https://github.com/BigTiger2020/74CMS/blob/main/07.png)  

The fetch() method was called  
![image](https://github.com/BigTiger2020/74CMS/blob/main/08.png)    

in /ThinkPHP/Library/Think/Template.class.php  
![image](https://github.com/BigTiger2020/74CMS/blob/main/09.png)   

Enter compiler method,in /ThinkPHP/Library/Think/Template.class.php   
![image](https://github.com/BigTiger2020/74CMS/blob/main/10.png)  

Returns the loadtemplate method  
![image](https://github.com/BigTiger2020/74CMS/blob/main/11.png)    

in /ThinkPHP/Library/Think/Storage/Driver/File.class.php  
![image](https://github.com/BigTiger2020/74CMS/blob/main/12.png)   


