Dependencies
	/src/main/java
	/target
	pom.xml

Folder Structure
	/src/main/java
	/src/main/resources
	/src/test/java
	/target

Pom Structure
	<project>
		<groupId>com.mohan<groupId>
		<artifaceId>blog<artifaceId>
		<version>1.0-SNAPSHOT<version>
		<modelVersion>4.0<modelVersion>
		<packaging>war</packaging>

		<dependencies>
			<dependency>
				<groupId>commons-lang<groupId>
				<artifaceId>commons-lang<artifaceId>
				<version>2.1<version>
			</dependency>
		</dependencies>

		<build>
			<finalName>test</finalName>

			<plugins>
				<plugin>
					<groupId>org.apache.maven.plugins</groupId>
					<artifactId>maven-compiler-plugin</artifactId>
					<version>2.5.1</version>
					<configuration>
						<fork>true</fork>
						<meminital>128m</meminital>
						<maxmem>512m</maxmem>
						<source>1.8</source>
						<target><1.8></target>
					<configuration>
				<plugin>
			<plugins>
		</build>

		<repositories>
			<repository>
				<id>mohan-snapshot<id>
				<name>mohan project snapshot repository<name
				<url>https://mohan.com/repo</url>
				<snapshots>
					<enabled>true
				</snapshots>
				<releases>
					<enabled>false
				</releases>
			</repository>
		</repositories>
	</project>

	id, name are user give

SNAPSHOT
	No need to rerelease for development
	Causes the dependency to be downloaded when there is a change

Goals
	clean - deletes files in /target directory
	compile
	test
	package - runs compile, runs test and creates package in /target
	install - runs package and installs in local repository
	deploy - runs install and copys to corporate repository

Types
	pom, maven-plugin, jar, ejb, war, ear, rar, par

Scope
	compile - default, available in all phases
	provided - available in all phases but not in final product, so it should be provided where it is deployed
	runtime - not needed for compilation but needed for execution
	test - only required for testing
	system - dont use. Hard code path to artifact location in file system

	<dependency>
		<groupId>junit<groupId>
		<artifaceId>junit<artifaceId>
		<version>4.1<version>
		<scope>test</scope>
	</dependency>

Repository
	http accessible location to download file from
	multiple repositories allowed
	Dependency repo and	Plugin repo
	Local repo - ~/.m2/repository/<artifactId>/<groupId>/<version>/
	Super pom.xml - found in default maven install

Plugins
	Phugins can have several goals
	Default goals like compile, test, package etc are part of super pom / default install
	Goals are ties to phase
	Phases - validate, compile, test, package, integration-test, verify, install, deploy
	Configurations/Execution
		Compiler - jre version
		Jar - includes/excludes, manifest
		Javadoc and Source - which phase and goal should the source be attached

