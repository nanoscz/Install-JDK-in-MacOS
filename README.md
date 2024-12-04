# Installing JDK on macOS

This guide explains how to download, install, configure, and verify the Java Development Kit (JDK) on macOS.

---

## 1. Downloading JDK

Visit the official Oracle website to download the JDK:

**URL:** [Oracle JDK Downloads](https://www.oracle.com/java/technologies/downloads/)

![JDK Download for macOS](/images/jdk-download-macos.png)

---

## 2. Verifying Installed JDK Version

After installation, you can verify the installed JDK versions by running the following command in your terminal:

```bash
/usr/libexec/java_home -V
```

This will list all installed JDK versions on your system.

![JDK Versions](/images/jdk-version.png)

---

## 3. Configuring Environment Variables

If you are using `zsh` (default shell in macOS since Catalina), update your `.zshrc` file to set the `JAVA_HOME` environment variable.

### Steps:

1. Open the `.zshrc` file:
   ```bash
   open .zshrc
   ```
2. Add the following lines to configure `JAVA_HOME`:

   ```bash
   export JAVA_HOME=$(/usr/libexec/java_home -v <version>)
   export PATH=$JAVA_HOME/bin:$PATH
   ```

   Replace `<version>` with the specific version of JDK you installed (e.g., `21.0.1` or `23.0.1`).

3. Save and close the file.

4. Apply the changes:
   ```bash
   source ~/.zshrc
   ```

---

## 4. Verifying the Java Installation

After configuring the environment, verify the Java version by running:

```bash
java --version
```

You should see output similar to this:

![Java Version Output](/images/java-version.png)

---

## 5. Testing the JDK Installation

To ensure your JDK is working correctly, follow these steps:

### 5.1. Create a Test Java File

Create a file named `Hello.java`:

```bash
touch Hello.java
```

### 5.2. Add the Following Code to `Hello.java`:

```java
public class Hello {
    public static void main(String[] args) {
        System.out.println("Hello, World!");
    }
}
```

### 5.3. Compile and Run the Java File

Run the following command to execute the Java program:

```bash
java Hello.java
```

### 5.4. Expected Output

The terminal should display:

```
Hello, World!
```

---

## Summary

You have successfully installed and configured JDK on macOS. By following the steps above, you can now use Java for your development needs. If you encounter issues, revisit the steps or consult the [Oracle JDK Documentation](https://www.oracle.com/java/technologies/javase-documentation.html).
