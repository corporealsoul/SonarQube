anup@automation-and-continuous-delivery:~$ git clone https://github.com/corporealsoul/CLI-Interactive-Maven-JAR-2024.git
anup@automation-and-continuous-delivery:~$ mvn archetype:generate
2163: remote -> org.apache.maven.archetypes:maven-archetype-webapp (An archetype which contains a sample Maven Webapp project.)
Choose a number or apply filter (format: [groupId:]artifactId, case sensitive contains): 2158: 2158
2158: remote -> org.apache.maven.archetypes:maven-archetype-quickstart (An archetype which contains a sample Maven project.)
Choose a number: 8: 8
Define value for property 'groupId': com.cliinteractivemavenjar2024
Define value for property 'artifactId': CLI-Interactive-Maven-JAR-2024
Define value for property 'version' 1.0-SNAPSHOT: : 1.0-SNAPSHOT
Define value for property 'package' com.cliinteractivemavenjar2024: : com.cliinteractivemavenjar2024.app
Confirm properties configuration:
groupId: com.cliinteractivemavenjar2024
artifactId: CLI-Interactive-Maven-JAR-2024
version: 1.0-SNAPSHOT
package: com.cliinteractivemavenjar2024.app
 Y: : Y

Maven build lifecyle :
anup@automation-and-continuous-delivery:~$ cd CLI-Interactive-Maven-JAR-2024/
Clean : anup@automation-and-continuous-delivery:~/CLI-Interactive-Maven-JAR-2024$ mvn clean
Validate : anup@automation-and-continuous-delivery:~/CLI-Interactive-Maven-JAR-2024$ mvn validate
Compile : anup@automation-and-continuous-delivery:~/CLI-Interactive-Maven-JAR-2024$ mvn compile
Test : anup@automation-and-continuous-delivery:~/CLI-Interactive-Maven-JAR-2024$ mvn test
Package : anup@automation-and-continuous-delivery:~/CLI-Interactive-Maven-JAR-2024$ mvn package
Verify : anup@automation-and-continuous-delivery:~/CLI-Interactive-Maven-JAR-2024$ mvn verify
Install : anup@automation-and-continuous-delivery:~/CLI-Interactive-Maven-JAR-2024$ mvn install

Deploy

Goals : clean validate compile test package verify install


Maven Dependencies,
https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html
https://mvnrepository.com/