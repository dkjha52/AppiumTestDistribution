# AppiumTestDistribution

Add the below dependencies in your pom.xml

```
<dependency>
	<groupId>com.appium.android</groupId>
	<artifactId>TestDistribution</artifactId>
	<version>0.0.6-SNAPSHOT</version>
</dependency>
```

```
<repositories>
		<repository>
			<id>saikrishna321</id>
			<name>maven-repo</name>
			<url>https://github.com/saikrishna321/maven-repo/tree/master/</url>
		</repository>
</repositories>
```
<h2>Sample Tests</h2>
 Clone the project (https://github.com/saikrishna321/AppiumTestDistributionExample)
<h1>Configure tests</h1>

Main class should look as below :: 

```
public class Runner {
    
	public static void main(String[] args) throws Exception {
		ParallelThread parallelThread = new ParallelThread();
		parallelThread.runner("com.yourpackage.to.tests");
	}
}

```

1. Extend your tests to BaseTest which is part of the dependencies, which takes care of running the appium server session in parallel threads.

2. Place your android.apk file into build folder.

3. add the below variables to the config.properties
 
    * appname=AndroidCalculator.apk(Android APK file name which is placed in build folder)
    * package=com.android2.calculator3(Application package)
    * appActivity=com.android2.calculator3.Calculator(Application Launch Activity)
    
    
<h3>Run Test from CommandLine</h3>

   mvn -Dtest=Runner test
   
<Allure report generation>

1. Install the CLI (http://wiki.qatools.ru/display/AL/Allure+Commandline)

2. Once the test is completed, run the command 
	* allure generate target/allure-results
	* allure report open

