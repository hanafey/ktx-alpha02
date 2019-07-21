Problem with 'androidx.core:core-ktx:1.2.0-alpha02'
===================================================

Steps to Reproduce
------------------
~~~~~~~
$ ./gradlew build
Starting a Gradle Daemon (subsequent builds will be faster)

> Transform artifact core.aar (androidx.core:core:1.2.0-alpha02) with DexingTransform
AGPBI: {"kind":"error","text":"Default interface methods are only supported starting with Android N (--min-api 24): android.view.MenuItem androidx.core.internal.view.SupportMenuItem.setContentDescription(java.lang.CharSequence)","sources":[{}],"tool":"D8"}

> Task :app:mergeExtDexDebug FAILED

FAILURE: Build failed with an exception.

* What went wrong:
Execution failed for task ':app:mergeExtDexDebug'.
> Could not resolve all files for configuration ':app:debugRuntimeClasspath'.
   > Failed to transform artifact 'core.aar (androidx.core:core:1.2.0-alpha02)' to match attributes {artifactType=android-dex, dexing-is-debuggable=true, dexing-min-sdk=22}
      > Execution failed for DexingTransform: /home/mkh/.gradle/caches/transforms-2/files-2.1/5488b352544db8edcd3b40cf2311303a/jetified-classes.jar.
         > Error while dexing.
   > Failed to transform artifact 'core.aar (androidx.core:core:1.2.0-alpha02)' to match attributes {artifactType=android-dex, dexing-is-debuggable=true, dexing-min-sdk=22}
      > Execution failed for DexingTransform: /home/mkh/.gradle/caches/transforms-2/files-2.1/5488b352544db8edcd3b40cf2311303a/jetified-classes.jar.
         > Error while dexing.
   > Failed to transform artifact 'core.aar (androidx.core:core:1.2.0-alpha02)' to match attributes {artifactType=android-dex, dexing-is-debuggable=true, dexing-min-sdk=22}
      > Execution failed for DexingTransform: /home/mkh/.gradle/caches/transforms-2/files-2.1/5488b352544db8edcd3b40cf2311303a/jetified-classes.jar.
         > Error while dexing.
   > Failed to transform artifact 'core.aar (androidx.core:core:1.2.0-alpha02)' to match attributes {artifactType=android-dex, dexing-is-debuggable=true, dexing-min-sdk=22}
      > Execution failed for DexingTransform: /home/mkh/.gradle/caches/transforms-2/files-2.1/5488b352544db8edcd3b40cf2311303a/jetified-classes.jar.
         > Error while dexing.
   > Failed to transform artifact 'core.aar (androidx.core:core:1.2.0-alpha02)' to match attributes {artifactType=android-dex, dexing-is-debuggable=true, dexing-min-sdk=22}
      > Execution failed for DexingTransform: /home/mkh/.gradle/caches/transforms-2/files-2.1/5488b352544db8edcd3b40cf2311303a/jetified-classes.jar.
         > Error while dexing.
   > Failed to transform artifact 'core.aar (androidx.core:core:1.2.0-alpha02)' to match attributes {artifactType=android-dex, dexing-is-debuggable=true, dexing-min-sdk=22}
      > Execution failed for DexingTransform: /home/mkh/.gradle/caches/transforms-2/files-2.1/5488b352544db8edcd3b40cf2311303a/jetified-classes.jar.
         > Error while dexing.
   > Failed to transform artifact 'core.aar (androidx.core:core:1.2.0-alpha02)' to match attributes {artifactType=android-dex, dexing-is-debuggable=true, dexing-min-sdk=22}
      > Execution failed for DexingTransform: /home/mkh/.gradle/caches/transforms-2/files-2.1/5488b352544db8edcd3b40cf2311303a/jetified-classes.jar.
         > Error while dexing.
   > Failed to transform artifact 'core.aar (androidx.core:core:1.2.0-alpha02)' to match attributes {artifactType=android-dex, dexing-is-debuggable=true, dexing-min-sdk=22}
      > Execution failed for DexingTransform: /home/mkh/.gradle/caches/transforms-2/files-2.1/5488b352544db8edcd3b40cf2311303a/jetified-classes.jar.
         > Error while dexing.
   > Failed to transform artifact 'core.aar (androidx.core:core:1.2.0-alpha02)' to match attributes {artifactType=android-dex, dexing-is-debuggable=true, dexing-min-sdk=22}
      > Execution failed for DexingTransform: /home/mkh/.gradle/caches/transforms-2/files-2.1/5488b352544db8edcd3b40cf2311303a/jetified-classes.jar.
         > Error while dexing.
   > Failed to transform artifact 'core.aar (androidx.core:core:1.2.0-alpha02)' to match attributes {artifactType=android-dex, dexing-is-debuggable=true, dexing-min-sdk=22}
      > Execution failed for DexingTransform: /home/mkh/.gradle/caches/transforms-2/files-2.1/5488b352544db8edcd3b40cf2311303a/jetified-classes.jar.
         > Error while dexing.

* Try:
Run with --stacktrace option to get the stack trace. Run with --info or --debug option to get more log output. Run with --scan to get full insights.

* Get more help at https://help.gradle.org

Deprecated Gradle features were used in this build, making it incompatible with Gradle 6.0.
Use '--warning-mode all' to show the individual deprecation warnings.
See https://docs.gradle.org/5.1.1/userguide/command_line_interface.html#sec:command_line_warnings

BUILD FAILED in 41s
36 actionable tasks: 16 executed, 20 up-to-date
~~~~~~~


Previous release of library does not have the problem
-----------------------------------------------------

Change the library to `androidx.core:core-ktx:1.2.0-alpha01` and the problem goes away.
~~~~~
$ ./gradlew build

> Task :app:lint
Ran lint on variant release: 4 issues found
Ran lint on variant debug: 4 issues found
Wrote HTML report to file:///home/mkh/AndroidStudioProjects/Bugs/ktx-alpha02/app/build/reports/lint-results.html
Wrote XML report to file:///home/mkh/AndroidStudioProjects/Bugs/ktx-alpha02/app/build/reports/lint-results.xml

Deprecated Gradle features were used in this build, making it incompatible with Gradle 6.0.
Use '--warning-mode all' to show the individual deprecation warnings.
See https://docs.gradle.org/5.1.1/userguide/command_line_interface.html#sec:command_line_warnings

BUILD SUCCESSFUL in 59s
58 actionable tasks: 39 executed, 19 up-to-date
mkh@rock:~/AndroidStudioProjects/Bugs/ktx-alpha02
~~~~~

Change the library back to `androidx.core:core-ktx:1.2.0-alpha02` and the problem returns, although reported somewhat
differently.

~~~~~
$ ./gradlew build

> Transform artifact core.aar (androidx.core:core:1.2.0-alpha02) with DexingTransform
AGPBI: {"kind":"error","text":"Default interface methods are only supported starting with Android N (--min-api 24): android.view.MenuItem androidx.core.internal.view.SupportMenuItem.setContentDescription(java.lang.CharSequence)","sources":[{}],"tool":"D8"}

> Task :app:mergeExtDexDebug FAILED

> Transform artifact core.aar (androidx.core:core:1.2.0-alpha02) with DexingTransform
AGPBI: {"kind":"error","text":"Default interface methods are only supported starting with Android N (--min-api 24): android.view.MenuItem androidx.core.internal.view.SupportMenuItem.setContentDescription(java.lang.CharSequence)","sources":[{}],"tool":"D8"}

FAILURE: Build failed with an exception.

* What went wrong:
Execution failed for task ':app:mergeExtDexDebug'.
> Could not resolve all files for configuration ':app:debugRuntimeClasspath'.
   > Failed to transform artifact 'core.aar (androidx.core:core:1.2.0-alpha02)' to match attributes {artifactType=android-dex, dexing-is-debuggable=true, dexing-min-sdk=22}
      > Execution failed for DexingTransform: /home/mkh/.gradle/caches/transforms-2/files-2.1/5488b352544db8edcd3b40cf2311303a/jetified-classes.jar.
         > Error while dexing.
   > Failed to transform artifact 'core.aar (androidx.core:core:1.2.0-alpha02)' to match attributes {artifactType=android-dex, dexing-is-debuggable=true, dexing-min-sdk=22}
      > Execution failed for DexingTransform: /home/mkh/.gradle/caches/transforms-2/files-2.1/5488b352544db8edcd3b40cf2311303a/jetified-classes.jar.
         > Error while dexing.
   > Failed to transform artifact 'core.aar (androidx.core:core:1.2.0-alpha02)' to match attributes {artifactType=android-dex, dexing-is-debuggable=true, dexing-min-sdk=22}
      > Execution failed for DexingTransform: /home/mkh/.gradle/caches/transforms-2/files-2.1/5488b352544db8edcd3b40cf2311303a/jetified-classes.jar.
         > Error while dexing.
   > Failed to transform artifact 'core.aar (androidx.core:core:1.2.0-alpha02)' to match attributes {artifactType=android-dex, dexing-is-debuggable=true, dexing-min-sdk=22}
      > Execution failed for DexingTransform: /home/mkh/.gradle/caches/transforms-2/files-2.1/5488b352544db8edcd3b40cf2311303a/jetified-classes.jar.
         > Error while dexing.
   > Failed to transform artifact 'core.aar (androidx.core:core:1.2.0-alpha02)' to match attributes {artifactType=android-dex, dexing-is-debuggable=true, dexing-min-sdk=22}
      > Execution failed for DexingTransform: /home/mkh/.gradle/caches/transforms-2/files-2.1/5488b352544db8edcd3b40cf2311303a/jetified-classes.jar.
         > Error while dexing.
   > Failed to transform artifact 'core.aar (androidx.core:core:1.2.0-alpha02)' to match attributes {artifactType=android-dex, dexing-is-debuggable=true, dexing-min-sdk=22}
      > Execution failed for DexingTransform: /home/mkh/.gradle/caches/transforms-2/files-2.1/5488b352544db8edcd3b40cf2311303a/jetified-classes.jar.
         > Error while dexing.
   > Failed to transform artifact 'core.aar (androidx.core:core:1.2.0-alpha02)' to match attributes {artifactType=android-dex, dexing-is-debuggable=true, dexing-min-sdk=22}
      > Execution failed for DexingTransform: /home/mkh/.gradle/caches/transforms-2/files-2.1/5488b352544db8edcd3b40cf2311303a/jetified-classes.jar.
         > Error while dexing.
   > Failed to transform artifact 'core.aar (androidx.core:core:1.2.0-alpha02)' to match attributes {artifactType=android-dex, dexing-is-debuggable=true, dexing-min-sdk=22}
      > Execution failed for DexingTransform: /home/mkh/.gradle/caches/transforms-2/files-2.1/5488b352544db8edcd3b40cf2311303a/jetified-classes.jar.
         > Error while dexing.
   > Failed to transform artifact 'core.aar (androidx.core:core:1.2.0-alpha02)' to match attributes {artifactType=android-dex, dexing-is-debuggable=true, dexing-min-sdk=22}
      > Execution failed for DexingTransform: /home/mkh/.gradle/caches/transforms-2/files-2.1/5488b352544db8edcd3b40cf2311303a/jetified-classes.jar.
         > Error while dexing.
   > Failed to transform artifact 'core.aar (androidx.core:core:1.2.0-alpha02)' to match attributes {artifactType=android-dex, dexing-is-debuggable=true, dexing-min-sdk=22}
      > Execution failed for DexingTransform: /home/mkh/.gradle/caches/transforms-2/files-2.1/5488b352544db8edcd3b40cf2311303a/jetified-classes.jar.
         > Error while dexing.

* Try:
Run with --stacktrace option to get the stack trace. Run with --info or --debug option to get more log output. Run with --scan to get full insights.

* Get more help at https://help.gradle.org

Deprecated Gradle features were used in this build, making it incompatible with Gradle 6.0.
Use '--warning-mode all' to show the individual deprecation warnings.
See https://docs.gradle.org/5.1.1/userguide/command_line_interface.html#sec:command_line_warnings

BUILD FAILED in 11s
39 actionable tasks: 20 executed, 19 up-to-date
~~~~~

Links
-----

Issue report: <https://issuetracker.google.com/issues/135628816>
GitHub: <https://github.com/hanafey/ktx-alpha02/tree/Reported>
