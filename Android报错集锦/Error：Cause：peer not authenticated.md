> **Error:Cause: peer not authenticated.**

**错误提示信息:**
``` java
Gradle '<ProjectName>' project refresh failed
     Error:Cause: peer not authenticated.
```

**错误原因：** 
Gradle version was not correct in project build.gradle file.
I had classpath 'com.android.tools.build:gradle:1.0.0'
but this needed to be classpath 'com.android.tools.build:gradle:1.1.0'