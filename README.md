





Gradle 설정(build.gradle) 
springframework 버전 2.4.11 (최신버전)
 sts 사용에 따른 이클립스 id 설정 
사내 경우 :  maven 레파지토리 설정 ,하단 mavenCenteral() 주석 처리 
사외 인경우 사내 반대로 주석처리 필요. 

Gradle 셋팅 (settings.gradle)
사내 인 경우 pluginManagement 설정 주석 해제
사외 인 경우 rootProject.name ='demo' 부분 주석 처리

   3. 윈도우 proxy 설정 

4. 사내에서 SDS.cert 설정 

gradle 프로젝트 임포트 Build Model 시  다음과 같은 오류 발생 시

java.lang.reflect.InvocationTargetException
...
Caused by: sun.security.provider.certpath.SunCertPathBuilderException: unable to find valid certification path to requested target
...




다음과 같이 설정 (암호: changeit )

keytool -keystore "%JAVA_HOME%/jre/lib/security/cacerts" -importcert -alias SDS -file C:\SDS.crt




5.Gradle properties 파일 생성 (non proxy포함)

c:/..../gradle/    위치에 gradle.properties 파일 생성 후 아래 내용 추가 

systemProp.proxySet=true
systemProp.http.proxyHost=70.10.15.10
systemProp.http.proxyPort=8080
systemProp.http.nonProxyHosts=70.121.224.52
systemProp.https.proxyHost=70.10.15.10
systemProp.https.proxyPort=8080
systemProp.https.nonProxyHosts=70.121.224.52




기타 ] 초코 설치 (  환경 관련 설치 파일 지원) 




choco를 이용한 gradle 설치 




choco를 이용한 zulu(java 설치)
