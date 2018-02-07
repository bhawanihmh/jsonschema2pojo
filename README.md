# jsonschema2pojo
Generate POJO from JSON including validation in maven pom file

## pom.xml

<dependencies>
		<dependency>
			<groupId>commons-lang</groupId>
			<artifactId>commons-lang</artifactId>
			<version>2.4</version>
		</dependency>
		<dependency>
			<groupId>com.fasterxml.jackson.core</groupId>
			<artifactId>jackson-databind</artifactId>
			<version>2.5.4</version>
		</dependency>
		<!-- https://mvnrepository.com/artifact/javax.validation/validation-api -->
		<dependency>
			<groupId>javax.validation</groupId>
			<artifactId>validation-api</artifactId>
			<version>2.0.1.Final</version>
		</dependency>
	</dependencies>
  
  <build>
		<plugins>
			<plugin>
				<groupId>org.jsonschema2pojo</groupId>
				<artifactId>jsonschema2pojo-maven-plugin</artifactId>
				<version>0.4.37</version>
				<configuration>
					<sourceDirectory>${basedir}/src/main/resources/schema/aPoints</sourceDirectory>
					<targetPackage>com.bhawani.aPoints</targetPackage>
					<includeJsr303Annotations>true</includeJsr303Annotations>
					<includeHashcodeAndEquals>true</includeHashcodeAndEquals> 
					<includeConstructors>true</includeConstructors>
				</configuration>
				<executions>
					<execution>
						<goals>
							<goal>generate</goal>
						</goals>
					</execution>
				</executions>
			</plugin>
		</plugins>
	</build>
