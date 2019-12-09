# How to setup java junit testing frame work

### Download the .jar files by visiting [ThisUrl](https://github.com/junit-team/junit/wiki/Download-and-Install)

1- Click the link for `junit.jar` Find the row for the latest stable release then under the downloads column click `jar` link. This will download a file `junit-X.Y.jar`

2- Repeat this again and download the latest stable release for hamcrest `hamcrest-core-XX.YY.jar`

### Create a jUnit Home folder.
1- We need to create a folder and put the `.jars` you downloaded into this folder. I suggest creating a folder called java (or your project name) in your home directory by running `cd && mkdir {{project_name}}` 

2- Run `cp ~/Downloads/{junit-X.Y.jar,hamcrest-core-XX.YY.jar} ~/java/` to copy the two `.jars` there and make sure to replace X, Y, XX, YY accordingly

### Edit and Export in .bashrc || .zshrc.
1- Edit your classpath. We now need to edit our `.bash_profile` file to add these files to our classpath (if you are using zsh edit your .zshrc file)

2- Paste the below in you `.bash_profile` || `.zshrc`

```bash
export JUNIT_HOME="$HOME/java"
export PATH="$PATH:$JUNIT_HOME"
export CLASSPATH="$CLASSPATH:$JUNIT_HOME/junit-X.Y.jar:$JUNIT_HOME/hamcrest-core-XX.YY.jar"
```

3- Save

4- Test it works. Restart your terminal. Run `echo $CLASSPATH`, there should be no errors that complain that files are unable to be found

5- create a file called `anasTest.java` with:
```java
import junit.framework.TestCase;
public class anasTest extends TestCase {
  public void testTrue() {
    assertTrue(true);
  }
}
```

5- Now `cd` into the project directory and run `javac anasTest.java` 

6- Run java `org.junit.runner.JUnitCore anasTest` If everything is ok, then you will get an output like:
```bash
JUnit version x.xx

Time: 0.006

OK (1 test)
```
