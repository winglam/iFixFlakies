# iFixFlakies

This plugin automatically generates patches for order-dependent tests by finding and utilizing helper test methods in the test suite.
This plugin builds upon code from iDFlakies (https://github.com/idflakies/iDFlakies), and relies on detected order-dependent tests that iDFlakies finds.

# Quickstart

First, follow the instructions for iDFlakies to detect order-dependent tests and obtain passing and failing orders for them.
You will need the ```.dtfixingtools``` directory generated by iDFlakies.

After building the plugin, you can add the plugin to a Maven project by modifying the pom.xml.

```xml
<build>
    ...
    <plugins>
        ...
        <plugin>
            <groupId>edu.illinois.cs</groupId>
            <artifactId>testrunner-maven-plugin</artifactId>
            <version>1.0</version>
            <dependencies>
                <dependency>
                    <groupId>edu.illinois.cs</groupId>
                    <artifactId>ifixflakies</artifactId>
                    <version>1.0.0-SNAPSHOT</version>
                </dependency>
            </dependencies>
            <configuration>
                <className>edu.illinois.cs.dt.tools.fixer.CleanerFixerPlugin</className>
            </configuration>
        </plugin>
    </plugins>
</build>
```

(If you had modified the pom.xml to run iDFlakies, you will notice the two modifications are quite similar. You will need to change the existing modification for iDFlakies to be like this modification for iFixFlakies.)

Run the following command on the Maven project:
```
mvn testrunner:testplugin
```

# Cite

If you use iFixFlakies, please cite our corresponding [ESEC/FSE paper](http://mir.cs.illinois.edu/awshi2/publications/FSE2019.pdf):
```
@inproceedings{ShiETAL2019FSE,
    author    = {Shi, August and Lam, Wing and Oei, Reed and Xie, Tao and Marinov, Darko},
    title     = {{iFixFlakies}: {A} Framework for Automatically Fixing Order-Dependent Flaky Tests},
    booktitle = {ACM Joint European Software Engineering Conference and Symposium on the Foundations of Software Engineering},
    pages     = {545--555},
    year      = {2019},
}
```
