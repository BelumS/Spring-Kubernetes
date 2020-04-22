web/                                                                                                000755  000765  000024  00000000000 13331070152 012127  5                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         web/Dockerfile                                                                                      000644  000765  000024  00000000231 13327622173 014130  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         FROM openjdk:8-jdk-alpine
VOLUME /tmp
ARG JAR_FILE
COPY ${JAR_FILE} app.jar
ENTRYPOINT ["java","-jar","/app.jar","docker.for.mac.localhost:8081","3333"]
                                                                                                                                                                                                                                                                                                                                                                       web/._pom.xml                                                                                       000755  000765  000024  00000000600 13330642657 013676  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                             Mac OS X            	   2  N     �                                      ATTR      �     x                      com.apple.TextEncoding          com.apple.lastuseddate#PS      '   Y  7com.apple.metadata:kMDLabel_ubgunqrhd5a7dbky2svlmjcvs4   utf-8;134217984��P[    ���    �6>��J�bv�*�|�V�mg7x�%Qu7�L�'Yy��˺dB�����x�թ�a@�9�;�x�KR\��o�p�����s_�_���_���                                                                                                                                web/pom.xml                                                                                         000755  000765  000024  00000005311 13330642657 013465  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>2.0.1.RELEASE</version>
	</parent>
	<groupId>com.demo.kubernetes.springcloud</groupId>
	<artifactId>web</artifactId>
	<version>0.0.1-SNAPSHOT</version>

	<properties>
		<start-class>com.demo.kubernetes.springcloud.web.WebServer</start-class>
	</properties>
	<dependencyManagement>
		<dependencies>
			<dependency>
				<groupId>org.springframework.cloud</groupId>
				<artifactId>spring-cloud-dependencies</artifactId>
				<version>Finchley.RELEASE</version>
				<type>pom</type>
				<scope>import</scope>
			</dependency>
		</dependencies>
	</dependencyManagement>
	<dependencies>
		<dependency>
			<!-- Setup Spring Boot -->
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter</artifactId>
		</dependency>

		<dependency>
			<!-- Setup Spring MVC & REST, use Embedded Tomcat -->
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>

		<dependency>
			<!-- Setup Spring Data common components -->
			<groupId>org.springframework.data</groupId>
			<artifactId>spring-data-commons</artifactId>
		</dependency>

		<dependency>
			<!-- Testing starter -->
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
		</dependency>

		<dependency>
			<!-- Spring Cloud starter -->
			<groupId>org.springframework.cloud</groupId>
			<artifactId>spring-cloud-starter</artifactId>
		</dependency>

		<!-- Gson: Java to Json conversion -->
		<dependency>
			<groupId>com.google.code.gson</groupId>
			<artifactId>gson</artifactId>
			<version>2.8.5</version>
			<scope>compile</scope>
		</dependency>
	</dependencies>

	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
				<executions>
					<execution>
						<goals>
							<goal>repackage</goal>
						</goals>
					</execution>
				</executions>
			</plugin>
			<plugin>
				<groupId>com.spotify</groupId>
				<artifactId>dockerfile-maven-plugin</artifactId>
				<version>1.3.6</version>
				<configuration>
					<tag>web-service</tag>
					<repository>konuratdocker/spark-examples</repository>
					<imageTags>
						<imageTag>web-service</imageTag>
					</imageTags>
					<buildArgs>
						<JAR_FILE>target/${project.build.finalName}.jar</JAR_FILE>
					</buildArgs>
				</configuration>
			</plugin>
		</plugins>
	</build>
</project>
                                                                                                                                                                                                                                                                                                                       web/src/                                                                                            000755  000765  000024  00000000000 13331067066 012730  5                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         web/src/main/                                                                                       000755  000765  000024  00000000000 13003745270 013650  5                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         web/src/main/resources/                                                                             000755  000765  000024  00000000000 13323726121 015661  5                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         web/src/main/java/                                                                                  000755  000765  000024  00000000000 13003745270 014571  5                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         web/src/main/java/com/                                                                              000755  000765  000024  00000000000 13003745270 015347  5                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         web/src/main/java/com/demo/                                                                         000755  000765  000024  00000000000 13321455545 016301  5                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         web/src/main/java/com/demo/kubernetes/                                                              000755  000765  000024  00000000000 13321455553 020447  5                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         web/src/main/java/com/demo/kubernetes/springcloud/                                                  000755  000765  000024  00000000000 13003745270 022773  5                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         web/src/main/java/com/demo/kubernetes/springcloud/web/                                              000755  000765  000024  00000000000 13331067103 023544  5                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         web/src/main/java/com/demo/kubernetes/springcloud/web/._WebController.java                          000755  000765  000024  00000000343 13327613203 027413  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                             Mac OS X            	   2   �      �                                      ATTR       �   �                     �     com.apple.TextEncoding      �     com.apple.lastuseddate#PS    utf-8;134217984��P[    T~{                                                                                                                                                                                                                                                                                                 web/src/main/java/com/demo/kubernetes/springcloud/web/WebController.java                            000755  000765  000024  00000012376 13327613203 027207  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         package com.demo.kubernetes.springcloud.web;

import java.util.logging.Logger;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;
import com.google.gson.Gson;


@RestController
public class WebController {

	@Autowired
	protected WebService service;
	
	protected Logger logger = Logger.getLogger(WebController.class
			.getName());

	@Autowired
	public WebController(WebService service) {
		logger.info("WebController initiated");;
		this.service = service;
	}
	
	@RequestMapping(value = "/zip/getZipcodeInfo/{zipcode}", produces = { "text/html" })
	public String zipInfo(@PathVariable("zipcode") String zipcode) {
		Gson gson = new Gson();
		String response = service.getZipInfo(zipcode);
		logger.info(response);
		ZipCodeInfo info = gson.fromJson(response,ZipCodeInfo.class);
		
		StringBuilder result = new StringBuilder();
		result.append("<html><body>");
		if(info != null){
			result.append(info.toString());
		}
		result.append("</body></html>");
		return result.toString();
	}
	
	@RequestMapping(value = "/zip/getNearbyZipcodes/{zipcode}/{distance}", produces = { "text/html" })
	public String zipDistance(@PathVariable("zipcode") String zipcode,@PathVariable("distance") String distance) {
		Gson gson = new Gson();
		String response = service.getNearbyZipcodesWithinDistance(zipcode, distance);
		logger.info(response);
		ZipCodeWrapper zipCodes = gson.fromJson(response,ZipCodeWrapper.class);
		StringBuilder result = new StringBuilder();
		result.append("<html><body>");
		if(zipCodes != null){
			result.append(zipCodes.toString());
		}
		result.append("</body></html>");
		return result.toString();
	}
}

class ZipCodeWrapper{
	ZipCode[] zip_codes;

	public ZipCode[] getZip_codes() {
		return zip_codes;
	}

	public void setZip_codes(ZipCode[] zip_codes) {
		this.zip_codes = zip_codes;
	}

	public String toString() {
		StringBuilder strBldr = new StringBuilder();
		strBldr.append("<p>Zip codes:<br>"); 
		for(ZipCode zipCode:zip_codes){
			strBldr.append(zipCode);
		}
		return strBldr.toString();
	}
}

class ZipCode {
	String zip_code;
	String distance;
	String city;
	String state;
	public String getZip_code() {
		return zip_code;
	}
	public void setZip_code(String zip_code) {
		this.zip_code = zip_code;
	}
	public String getDistance() {
		return distance;
	}
	public void setDistance(String distance) {
		this.distance = distance;
	}
	public String getCity() {
		return city;
	}
	public void setCity(String city) {
		this.city = city;
	}
	public String getState() {
		return state;
	}
	public void setState(String state) {
		this.state = state;
	}
	
	public String toString() {
		return "<p>zip_code=" + zip_code + ", distance=" + distance + " miles, city=" + city + ", state=" + state;
	}
}


class ZipCodeInfo {
	String zip_code;
	String lat;
	String lng;
	String city;
	String state;
	CityState[] acceptable_city_names;
	Timezone timezone;
	
	public String getZip_code() {
		return zip_code;
	}

	public void setZip_code(String zip_code) {
		this.zip_code = zip_code;
	}

	public String getLat() {
		return lat;
	}

	public void setLat(String lat) {
		this.lat = lat;
	}

	public String getLng() {
		return lng;
	}

	public void setLng(String lng) {
		this.lng = lng;
	}

	public String getCity() {
		return city;
	}

	public void setCity(String city) {
		this.city = city;
	}

	public String getState() {
		return state;
	}

	public void setState(String state) {
		this.state = state;
	}

	
	
	public Timezone getTimezone() {
		return timezone;
	}

	public void setTimezone(Timezone timezone) {
		this.timezone = timezone;
	}



	class Timezone{
		String timezone_identifier;
		String timezone_abbr;
		public String getTimezone_identifier() {
			return timezone_identifier;
		}
		public void setTimezone_identifier(String timezone_identifier) {
			this.timezone_identifier = timezone_identifier;
		}
		public String getTimezone_abbr() {
			return timezone_abbr;
		}
		public void setTimezone_abbr(String timezone_abbr) {
			this.timezone_abbr = timezone_abbr;
		}
		
		public String toString() {
			return "<p>Timezone: " + timezone_identifier + " (" + timezone_abbr + ")";
		}
	}
	
	class CityState{
		String city;
		String state;
		public String getCity() {
			return city;
		}
		public void setCity(String city) {
			this.city = city;
		}
		public String getState() {
			return state;
		}
		public void setState(String state) {
			this.state = state;
		}
		
		public String toString() {
			return "<p>City: " + city + ", State: " + state;
		}	
	}

	public CityState[] getAcceptable_city_names() {
		return acceptable_city_names;
	}

	public void setAcceptable_city_names(CityState[] acceptable_city_names) {
		this.acceptable_city_names = acceptable_city_names;
	}

	
	public String toString() {
		StringBuilder strBldr = new StringBuilder();
		strBldr.append("<p>Zipcode Information:<p>zip: " + zip_code + ", latitude: " + lat + ", longitude: " + lng + ", city: " + city + ", state: "
				+ state);
		strBldr.append(timezone);
		strBldr.append("<p>Acceptable City Names:");
		for(CityState cityState:acceptable_city_names){
			strBldr.append("<p>" + cityState.getCity() + ", " + cityState.getState());
		}
		return strBldr.toString();
	}
}

                                                                                                                                                                                                                                                                  web/src/main/java/com/demo/kubernetes/springcloud/web/._WebServer.java                              000755  000765  000024  00000000343 13324170055 026536  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                             Mac OS X            	   2   �      �                                      ATTR       �   �                     �     com.apple.TextEncoding      �     com.apple.lastuseddate#PS    utf-8;134217984�ZG[    zT�:                                                                                                                                                                                                                                                                                                 web/src/main/java/com/demo/kubernetes/springcloud/web/WebServer.java                                000755  000765  000024  00000002631 13324170055 026323  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         package com.demo.kubernetes.springcloud.web;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.cloud.client.discovery.EnableDiscoveryClient;
import org.springframework.context.annotation.Bean;
import org.springframework.context.annotation.ComponentScan;
import org.springframework.web.client.RestTemplate;

@SpringBootApplication
@EnableDiscoveryClient
@ComponentScan(useDefaultFilters = false)
public class WebServer {
	
	public static String web_service_url = null;
	
	public static void main(String[] args) {
		if(args.length != 1 && args.length != 2){
			errorMessage();
			return;
		}else if(args.length == 2){
			web_service_url = args[0];
			System.setProperty("server.port", args[1]);
		}else if(args.length == 1){
			web_service_url = args[0];
		}
		System.setProperty("spring.config.name", "web-server");
		SpringApplication.run(WebServer.class, args);
	}
	
	@Bean
	RestTemplate restTemplate() {
		return new RestTemplate();
	}
	
	@Bean
	public WebService service() {
		return new WebService(web_service_url);
	}
	
	@Bean
	public WebController patientController() {
		return new WebController(service());
	}
	
	protected static void errorMessage() {
		System.out.println("Usage: java -jar [jar file name] <zip web service url> <port> OR");
		System.out.println("Usage: java -jar [jar file name] <zip web service url>");
	}
}
                                                                                                       web/src/main/java/com/demo/kubernetes/springcloud/web/._WebService.java                             000755  000765  000024  00000000600 13330634411 026662  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                             Mac OS X            	   2  N     �                                      ATTR      �     x                      com.apple.TextEncoding          com.apple.lastuseddate#PS      '   Y  7com.apple.metadata:kMDLabel_ubgunqrhd5a7dbky2svlmjcvs4   utf-8;134217984�ZG[    q�    �	��3ǙP�	�<����u��'%_W~�n ì���㰒S�v\���w͏��Do��ϧ�~5�Do3-��-4�$���=���)� �T                                                                                                                                web/src/main/java/com/demo/kubernetes/springcloud/web/WebService.java                               000755  000765  000024  00000001755 13330634411 026461  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         package com.demo.kubernetes.springcloud.web;

import java.util.logging.Logger;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.stereotype.Service;
import org.springframework.web.client.RestTemplate;

@Service
public class WebService {
	
	@Autowired
	protected RestTemplate restTemplate;

	protected String serviceUrl;

	protected Logger logger = Logger.getLogger(WebService.class
			.getName());

	/**
	 * The serviceURL parameter corresponds to the zipcode service.
	 * @param String serviceURL
	 */
	public WebService(String serviceURL) {
		this.serviceUrl = "http://"+serviceURL;
	}
	
	public String getZipInfo(String zipcode){
		return restTemplate.getForObject(serviceUrl
				+ "/zipcodeservice/info/{zipcode}", String.class, zipcode);
	}
	
	public String getNearbyZipcodesWithinDistance(String zipcode,String distance){
		return restTemplate.getForObject(serviceUrl
				+ "/zipcodeservice/nearby/{zipcode}/{distance}", String.class, zipcode,distance);
	}
}
                   web/src/main/resources/._logback.xml                                                                000755  000765  000024  00000000600 13322210776 020224  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                             Mac OS X            	   2  N     �                                      ATTR      �     x                      com.apple.TextEncoding          com.apple.lastuseddate#PS      '   Y  7com.apple.metadata:kMDLabel_ubgunqrhd5a7dbky2svlmjcvs4   utf-8;134217984�I[    l��(    ����j��iƑ�Ic�B���r�!�Bѓ�?�BHG�L��OLA(���g�j��O�d}*_�h8�aע���K�ZP�kC�ʙ<P\i�yJ                                                                                                                                web/src/main/resources/logback.xml                                                                  000755  000765  000024  00000001517 13322210776 020017  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         <?xml version="1.0" encoding="UTF-8"?>
<!-- configuration file for LogBack (slf4J implementation)
See here for more details: http://gordondickens.com/wordpress/2013/03/27/sawing-through-the-java-loggers/ -->
<configuration scan="true" scanPeriod="30 seconds">

    <contextListener class="ch.qos.logback.classic.jul.LevelChangePropagator">
        <resetJUL>true</resetJUL>
    </contextListener>

    <!-- To enable JMX Management -->
    <jmxConfigurator/>

    <appender name="console" class="ch.qos.logback.core.ConsoleAppender">
        <encoder>
            <pattern>${PID}: %-5level %logger{0} - %msg%n</pattern>
        </encoder>
    </appender>

    <!-- Specify logging levels -->
    <logger name="org.springframework" level="warn"/>
         
    <root level="info">
        <appender-ref ref="console"/>
    </root>
</configuration>
                                                                                                                                                                                 web/src/main/resources/._web-server.yml                                                             000755  000765  000024  00000000547 13324166516 020722  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                             Mac OS X            	   2  5     g                                      ATTR      g   �   �                  �   �  "com.apple.LaunchServices.OpenWith      W     com.apple.lastuseddate#PS    bplist00�WversionTpath_bundleidentifier _/Applications/Xcode.app_com.apple.dt.Xcode/1K                            `�I[    "'                                                                                                                                                             web/src/main/resources/web-server.yml                                                               000755  000765  000024  00000000152 13324166516 020475  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         spring:
  application:
    name: web-service  

# HTTP Server
server:
  port: 3333   # HTTP (Tomcat) port
                                                                                                                                                                                                                                                                                                                                                                                                                      zipcodeservice/                                                                                     000755  000765  000024  00000000000 13331070160 014367  5                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         zipcodeservice/._Dockerfile                                                                         000644  000765  000024  00000000260 13323452171 016603  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                             Mac OS X            	   2   ~      �                                      ATTR       �   �                     �     com.apple.lastuseddate#PS    CJR[    <k                                                                                                                                                                                                                                                                                                                                                    zipcodeservice/Dockerfile                                                                           000644  000765  000024  00000000171 13323452171 016367  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         FROM openjdk:8-jdk-alpine
VOLUME /tmp
ARG JAR_FILE
COPY ${JAR_FILE} app.jar
ENTRYPOINT ["java","-jar","/app.jar","2223"]
                                                                                                                                                                                                                                                                                                                                                                                                       zipcodeservice/._pom.xml                                                                            000644  000765  000024  00000000343 13323450217 016127  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                             Mac OS X            	   2   �      �                                      ATTR       �   �                     �     com.apple.TextEncoding      �     com.apple.lastuseddate#PS    utf-8;134217984��G[    ыD                                                                                                                                                                                                                                                                                                 zipcodeservice/pom.xml                                                                              000644  000765  000024  00000004544 13323450217 015721  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         <project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<parent>
		<groupId>org.springframework.cloud</groupId>
		<artifactId>spring-cloud-starter-parent</artifactId>
		<version>Finchley.RELEASE</version>
	</parent>
	<groupId>com.demo.kubernetes.springcloud</groupId>
	<artifactId>service</artifactId>
	<version>0.0.1-SNAPSHOT</version>

	<properties>
		<start-class>com.demo.kubernetes.springcloud.service.ZipcodeServer</start-class>
	</properties>

	<dependencies>
		<dependency>
			<!-- Setup Spring Boot -->
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter</artifactId>
		</dependency>

		<dependency>
			<!-- Setup Spring MVC & REST, use Embedded Tomcat -->
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>

		<dependency>
			<!-- Setup Spring Data common components -->
			<groupId>org.springframework.data</groupId>
			<artifactId>spring-data-commons</artifactId>
		</dependency>

		<dependency>
			<!-- Testing starter -->
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
		</dependency>


		<dependency>
			<!-- Spring Cloud starter -->
			<groupId>org.springframework.cloud</groupId>
			<artifactId>spring-cloud-starter</artifactId>
		</dependency>
	</dependencies>

	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
				<executions>
					<execution>
						<goals>
							<goal>repackage</goal>
						</goals>
					</execution>
				</executions>
			</plugin>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
			<plugin>
				<groupId>com.spotify</groupId>
				<artifactId>dockerfile-maven-plugin</artifactId>
				<version>1.3.6</version>
				<configuration>
					<tag>zipcode-service</tag>
					<repository>konuratdocker/spark-examples</repository>
					<imageTags>
						<imageTag>zipcode-service</imageTag>
					</imageTags>
					<buildArgs>
						<JAR_FILE>target/${project.build.finalName}.jar</JAR_FILE>
					</buildArgs>
				</configuration>
			</plugin>
		</plugins>
	</build>
</project>
                                                                                                                                                            zipcodeservice/src/                                                                                 000755  000765  000024  00000000000 13331067121 015161  5                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         zipcodeservice/src/main/                                                                            000755  000765  000024  00000000000 12757662541 016127  5                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         zipcodeservice/src/main/resources/                                                                  000755  000765  000024  00000000000 13331067127 020125  5                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         zipcodeservice/src/main/java/                                                                       000755  000765  000024  00000000000 12757663154 017051  5                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         zipcodeservice/src/main/java/com/                                                                   000755  000765  000024  00000000000 12757663154 017627  5                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         zipcodeservice/src/main/java/com/demo/                                                              000755  000765  000024  00000000000 13321447673 020545  5                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         zipcodeservice/src/main/java/com/demo/kubernetes/                                                   000755  000765  000024  00000000000 13321447704 022707  5                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         zipcodeservice/src/main/java/com/demo/kubernetes/springcloud/                                       000755  000765  000024  00000000000 13322176113 025232  5                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         zipcodeservice/src/main/java/com/demo/kubernetes/springcloud/service/                               000755  000765  000024  00000000000 13331070123 026664  5                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         zipcodeservice/src/main/java/com/demo/kubernetes/springcloud/service/ServiceConfiguration.java      000644  000765  000024  00000000667 13324166630 033703  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         package com.demo.kubernetes.springcloud.service;

import org.springframework.context.annotation.ComponentScan;
import org.springframework.context.annotation.Configuration;
import java.util.logging.Logger;

@Configuration
@ComponentScan
public class ServiceConfiguration {
	protected Logger logger;
	
	public ServiceConfiguration(){
		logger = Logger.getLogger(getClass().getName());
		logger.info("ServiceConfiguration initialized");
	}
}
                                                                         zipcodeservice/src/main/java/com/demo/kubernetes/springcloud/service/._ZipcodeServer.java           000644  000765  000024  00000000343 13323176736 032552  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                             Mac OS X            	   2   �      �                                      ATTR       �   �                     �     com.apple.TextEncoding      �     com.apple.lastuseddate#PS    utf-8;134217984+GR[    j�k8                                                                                                                                                                                                                                                                                                 zipcodeservice/src/main/java/com/demo/kubernetes/springcloud/service/ZipcodeServer.java             000644  000765  000024  00000001477 13323176736 032346  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         package com.demo.kubernetes.springcloud.service;

import java.util.logging.Logger;
import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class ZipcodeServer {

	protected Logger logger = Logger.getLogger(ZipcodeServer.class.getName());

	public static void main(String[] args) {
		if (args.length > 0 && args.length != 1) {
			errorMessage();
			return;
		} else if (args.length == 1) {
			System.setProperty("server.port", args[0]);
		}
		System.setProperty("spring.config.name", "zipcodeservice-server");
		SpringApplication.run(ZipcodeServer.class, args);
	}

	protected static void errorMessage() {
		System.out.println("Usage: java -jar [jar file name] <port> OR");
		System.out.println("Usage: java -jar [jar file name]");
	}
}
                                                                                                                                                                                                 zipcodeservice/src/main/java/com/demo/kubernetes/springcloud/service/._ServiceController.java       000644  000765  000024  00000000343 13331070123 033410  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                             Mac OS X            	   2   �      �                                      ATTR       �   �                     �     com.apple.TextEncoding      �     com.apple.lastuseddate#PS    utf-8;134217984�T[    �CD                                                                                                                                                                                                                                                                                                 zipcodeservice/src/main/java/com/demo/kubernetes/springcloud/service/ServiceController.java         000644  000765  000024  00000004157 13331070123 033202  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         package com.demo.kubernetes.springcloud.service;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.net.HttpURLConnection;
import java.net.MalformedURLException;
import java.net.URL;
import java.util.logging.Level;
import java.util.logging.Logger;
import org.springframework.beans.factory.annotation.Autowired;
import org.springframework.web.bind.annotation.PathVariable;
import org.springframework.web.bind.annotation.RequestMapping;
import org.springframework.web.bind.annotation.RestController;

@RestController
public class ServiceController {
	private static final String URLPrefix = "https://www.zipcodeapi.com/rest/REDACTED/";
	private static final String GET = "GET";
	
	protected Logger logger = Logger.getLogger(ServiceController.class.getName());

	@Autowired
	public ServiceController() {
		logger.info("ServiceController initiated");
	}

	@RequestMapping(value = "/zipcodeservice/info/{zipcode}", produces = { "application/json" })
	public String getZipcodeInfo(@PathVariable("zipcode") Integer zipcode) {
		return getURLResponse("info.json/" + zipcode + "/degrees");
	}

	@RequestMapping(value = "/zipcodeservice/nearby/{zipcode}/{distance}", produces = { "application/json" })
	public String getNearbyZipcodes(@PathVariable("zipcode") Integer zipcode,
			@PathVariable("distance") Integer distance) {
		return getURLResponse("radius.json/" + zipcode + "/" + distance + "/mile");
	}

	private String getURLResponse(String path) {
		try {
			URL url = new URL(URLPrefix + path);
			HttpURLConnection connection = (HttpURLConnection) url.openConnection();
			connection.setRequestMethod(GET);

			StringBuilder result = new StringBuilder();
			BufferedReader reader = new BufferedReader(new InputStreamReader(connection.getInputStream()));
			String line;
			while ((line = reader.readLine()) != null) {
				result.append(line);
			}
			reader.close();
			return result.toString();
		} catch (MalformedURLException e1) {
			logger.log(Level.SEVERE, e1.getMessage(), e1);
			return null;

		} catch (IOException e2) {
			logger.log(Level.SEVERE, e2.getMessage(), e2);
			return null;
		}
	}
}
                                                                                                                                                                                                                                                                                                                                                                                                                 zipcodeservice/src/main/resources/logback.xml                                                       000755  000765  000024  00000001246 13326666357 022275  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         <?xml version="1.0" encoding="UTF-8"?>
<configuration scan="true" scanPeriod="30 seconds">

    <contextListener class="ch.qos.logback.classic.jul.LevelChangePropagator">
        <resetJUL>true</resetJUL>
    </contextListener>

    <!-- To enable JMX Management -->
    <jmxConfigurator/>

    <appender name="console" class="ch.qos.logback.core.ConsoleAppender">
        <encoder>
            <pattern>${PID}: %-5level %logger{0} - %msg%n</pattern>
        </encoder>
    </appender>

    <!-- Specify logging levels -->
    <logger name="org.springframework" level="warn"/>
         
    <root level="info">
        <appender-ref ref="console"/>
    </root>
</configuration>
                                                                                                                                                                                                                                                                                                                                                          zipcodeservice/src/main/resources/._zipcodeservice-server.yml                                       000644  000765  000024  00000000260 13323176767 025421  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                             Mac OS X            	   2   ~      �                                      ATTR       �   �                     �     com.apple.lastuseddate#PS    8GR[    ��                                                                                                                                                                                                                                                                                                                                                    zipcodeservice/src/main/resources/zipcodeservice-server.yml                                         000644  000765  000024  00000000156 13323176767 025210  0                                                                                                    ustar 00konur                           staff                           000000  000000                                                                                                                                                                         spring:
  application:
     name: zipcode-service  

# HTTP Server
server:
  port: 2222   # HTTP (Tomcat) port                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  