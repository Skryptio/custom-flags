### General Filtering Criteria:
1. **Prohibited file extensions** (it blocks files with the following extensions):
   - **Any file with a 2-4 letter extension** (e.g., `.sh`, `.exe`, `.txt`), as the pattern `/\.[a-zA-Z0-9]{2,4}$/` matches and blocks these extensions.

2. **Blocked startup flags/commands**:
   - **Memory-related flags**:
     - `-Xms`
     - `-Xmx`
     - `-XX:MaxRAMPercentage`
     - Variations in case or formatting:
       - `-xms`, `-xmx`, `-XMX`, `-XMS`, `-xMs`, `-xMx`, `-xmX`, `-xmS`, `-XmS`, `-XmX`
   - **Java garbage collection and container support flags**:
     - `-XX:+UseContainerSupport`
     - `-XX:+UseZGC`
     - `-XX:+UseShenandoahGC`
   - **Miscellaneous flags and commands**:
     - `--illegal-access=`
     - `-Dlog4j2.formatMsgNoLookups=true`
     - `-agentlib:`
     - `-javaagent:`
     - `-Xdebug`
     - `-Xrunjdwp`
     - `java` (blocking the term `java` for security reasons)
     - `CLASSPATH`
     - `AllowAttachSelf`
     - `-XX:OnOutOfMemoryError`
     - `-XX:CompileCommand`
     - `-Xbootclasspath`
     - `-Dsun.boot.library.path`
     - `library`
     - `Archive`
     - `-Duser.language`
     - `-Djavax.net.ssl.trustStore`
     - `-Dsun.rmi.server.activation.debugExec`
     - `-Dcom.sun.management.jmxremote`
     - `-Dsun.awt.disablegrab=true`
     - `-Djava.system.class.loader`
     - `-Dsun.java2d.opengl`
     - `-Djava.security.policy`
     - `-Dsun.nio.ch.bugLevel`
     - `UsePerfData`
     - `-Dsun.tools.attach.attachTimeout`
     - `-Dfile.encoding`
     - `-Djava`
     - `-Dsun`
     - `-Dcom`
     - `-Djavax`
     - `-Djdk`
     - `-Duser`
     - `-Dos`
     - `-Dfile`
     - `-Dawt`

### Summary of Blocked Patterns:
- Memory-related flags with the patterns like `-Xms`, `-Xmx`, `-XX:MaxRAMPercentage`, including all variations.
- Java debug and agent-related flags: `-Xdebug`, `-javaagent`, `-Xrunjdwp`, etc.
- Various system and environment settings (like `-Djava`, `-Dsun`, `CLASSPATH`, etc.).
- Flags that affect garbage collection (`-XX:+UseContainerSupport`, `-XX:+UseZGC`, etc.).
- Other specific Java-related environment variables and commands that are often seen in unsafe or specialized configurations.
