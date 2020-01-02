# HowToSetHttpsTomcat
Tutorial of setting Https Tomcat
참고 사이트: https://lts0606.tistory.com/220

server.xml
변경전
<Connector port="8085" protocol="HTTP/1.1"
               connectionTimeout="20000"
               redirectPort="8443" />
변경후
 <Connector port="8085" protocol="org.apache.coyote.http11.Http11NioProtocol" 
 maxHttpHeaderSize="8192" maxThreads="150" 
 enableLookups="false" acceptCount="100" connectionTimeout="20000" 
 disableUploadTimeout="true"
 SSLEnabled="true" scheme="https" secure="true" clientAuth="false" sslProtocol="TLS" 
 keystoreFile="/path/to/.keystore" 
 keystorePass="password"
 />
