*********��������ʾͨ��maven��webģ������javaweb��Ŀ��*********
1��ͨ��maven��webģ������һ������
   �л���Ҫ��Ź��̵�Ŀ¼����E:\tmp>��ʹ�����E:\tmp>mvn archetype:generate -DgroupId=com.thg -DartifactId=maven4web -DarchetypeArtifactId=maven-archetype-webapp -DinteractiveMode=false��
������Ŀ ����׼��webĿ¼�ṹ���Զ��������ṹ����
|____maven4web
||____pom.xml
||____src
|||____main
||||____resources
||||____webapp
|||||____index.jsp
|||||____WEB-INF
||||||____web.xml

2������eclipse֧��
  �л������ɵĹ���Ŀ¼�£�ʹ�����E:\tmp\maven4web>mvn eclipse:eclipse -Dwtpversion=2.0������wtp������Ϊ�˽���Ŀת����web��Ŀ��war����Ĭ����java��Ŀ��jar��

3����eclipse�е��빤��
  �� Eclipse IDE�У������� File -> Import�� -> General -> Existing Projects into workspace �������빤��

4���޸�POM�����Ŀ�����Ͳ��
  ��pom.xml�������������Spring, logback �� JUnit���Ͳ����tomcat��jdk������Ҫ�ٴ�ִ�����E:\tmp\maven4web>mvn eclipse:eclipse������eclipse֧�֣�����Ҫ��wtp��������Ϊ��pom������������
  
5���޸Ĺ��̴���
  ����ʵ������������Ŀ¼����������ļ����޸Ĵ��룺
  5.1������ Spring MVC �Ŀ�������BaseController.java��
  5.2������Spring�����ļ�mvc-dispatcher-servlet.xml;
  5.3:�޸�web.xml ֧�� Servlet 2.5�������Spring ������ ContextLoaderListener ������Spring��ܣ�
  5.4���ƶ��ļ� index.jsp �� WEB-INF/pages Ŀ¼�£� Ϊ�˱���ֱ�ӷ���
  5.5������Դ�ļ���(resources)�д��� logback.xml �ļ�
|____pom.xml
|____src
| |____main
| | |____java
| | | |____com
| | | | |____yiibai
| | | | | |____controller
| | | | | | |____BaseController.java
| | |____resources
| | | |____logback.xml
| | |____webapp
| | | |____WEB-INF
| | | | |____mvc-dispatcher-servlet.xml
| | | | |____pages
| | | | | |____index.jsp
| | | | |____web.xml
  
  
6��ͨ��eclipse����Ŀ�����tomcat�����𷢲�����
  ͨ�����E:\tmp\maven4web>mvn eclipse:eclipse������eclipse֧�֣���ͨ�����E:\tmp\maven4web>mvn tomcat7:run����������������ע����tomcat7������ᱨ����
  