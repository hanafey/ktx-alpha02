Problem with 'androidx.core:core-ktx:1.2.0-alpha02'
===================================================

Steps to Reproduce
------------------
Attempt to run the app on a device running Android 5.1.1 API 22.

The following exception is generated:
~~~~~
AGPBI: {"kind":"error","text":"Default interface methods are only supported starting with Android N (--min-api 24): android.view.MenuItem androidx.core.internal.view.SupportMenuItem.setContentDescription(java.lang.CharSequence)","sources":[{}],"tool":"D8"}
> Task :app:transformClassesWithDexBuilderForDebug
com.android.builder.dexing.DexArchiveBuilderException: com.android.builder.dexing.DexArchiveBuilderException: Failed to process /home/mkh/.gradle/caches/transforms-2/files-2.1/269996e901f644d75b755f38d6670581/jars/classes.jar
	at sun.reflect.NativeConstructorAccessorImpl.newInstance0(Native Method)
	at sun.reflect.NativeConstructorAccessorImpl.newInstance(NativeConstructorAccessorImpl.java:62)
	at sun.reflect.DelegatingConstructorAccessorImpl.newInstance(DelegatingConstructorAccessorImpl.java:45)
	at java.lang.reflect.Constructor.newInstance(Constructor.java:423)
	at java.util.concurrent.ForkJoinTask.getThrowableException(ForkJoinTask.java:593)
	at java.util.concurrent.ForkJoinTask.reportException(ForkJoinTask.java:677)
	at java.util.concurrent.ForkJoinTask.join(ForkJoinTask.java:720)
	at com.android.ide.common.internal.WaitableExecutor.waitForTasksWithQuickFail(WaitableExecutor.java:149)
	at com.android.build.gradle.internal.transforms.DexArchiveBuilderTransform.transform(DexArchiveBuilderTransform.java:420)
	at com.android.build.gradle.internal.pipeline.TransformTask$2.call(TransformTask.java:239)
	at com.android.build.gradle.internal.pipeline.TransformTask$2.call(TransformTask.java:235)
	at com.android.builder.profile.ThreadRecorder.record(ThreadRecorder.java:102)
	at com.android.build.gradle.internal.pipeline.TransformTask.transform(TransformTask.java:230)
	at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
	at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
	at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
	at java.lang.reflect.Method.invoke(Method.java:498)
	at org.gradle.internal.reflect.JavaMethod.invoke(JavaMethod.java:73)
	at org.gradle.api.internal.project.taskfactory.IncrementalTaskAction.doExecute(IncrementalTaskAction.java:47)
	at org.gradle.api.internal.project.taskfactory.StandardTaskAction.execute(StandardTaskAction.java:41)
	at org.gradle.api.internal.project.taskfactory.StandardTaskAction.execute(StandardTaskAction.java:28)
	at org.gradle.api.internal.tasks.execution.ExecuteActionsTaskExecuter$2.run(ExecuteActionsTaskExecuter.java:284)
	at org.gradle.internal.operations.DefaultBuildOperationExecutor$RunnableBuildOperationWorker.execute(DefaultBuildOperationExecutor.java:301)
	at org.gradle.internal.operations.DefaultBuildOperationExecutor$RunnableBuildOperationWorker.execute(DefaultBuildOperationExecutor.java:293)
	at org.gradle.internal.operations.DefaultBuildOperationExecutor.execute(DefaultBuildOperationExecutor.java:175)
	at org.gradle.internal.operations.DefaultBuildOperationExecutor.run(DefaultBuildOperationExecutor.java:91)
	at org.gradle.internal.operations.DelegatingBuildOperationExecutor.run(DelegatingBuildOperationExecutor.java:31)
	at org.gradle.api.internal.tasks.execution.ExecuteActionsTaskExecuter.executeAction(ExecuteActionsTaskExecuter.java:273)
	at org.gradle.api.internal.tasks.execution.ExecuteActionsTaskExecuter.executeActions(ExecuteActionsTaskExecuter.java:258)
	at org.gradle.api.internal.tasks.execution.ExecuteActionsTaskExecuter.access$200(ExecuteActionsTaskExecuter.java:67)
	at org.gradle.api.internal.tasks.execution.ExecuteActionsTaskExecuter$TaskExecution.execute(ExecuteActionsTaskExecuter.java:145)
	at org.gradle.internal.execution.impl.steps.ExecuteStep.execute(ExecuteStep.java:49)
	at org.gradle.internal.execution.impl.steps.CancelExecutionStep.execute(CancelExecutionStep.java:34)
	at org.gradle.internal.execution.impl.steps.TimeoutStep.executeWithoutTimeout(TimeoutStep.java:69)
	at org.gradle.internal.execution.impl.steps.TimeoutStep.execute(TimeoutStep.java:49)
	at org.gradle.internal.execution.impl.steps.CatchExceptionStep.execute(CatchExceptionStep.java:33)
	at org.gradle.internal.execution.impl.steps.CreateOutputsStep.execute(CreateOutputsStep.java:50)
	at org.gradle.internal.execution.impl.steps.SnapshotOutputStep.execute(SnapshotOutputStep.java:43)
	at org.gradle.internal.execution.impl.steps.SnapshotOutputStep.execute(SnapshotOutputStep.java:29)
	at org.gradle.internal.execution.impl.steps.CacheStep.executeWithoutCache(CacheStep.java:134)
	at org.gradle.internal.execution.impl.steps.CacheStep.lambda$execute$3(CacheStep.java:83)
	at java.util.Optional.orElseGet(Optional.java:267)
	at org.gradle.internal.execution.impl.steps.CacheStep.execute(CacheStep.java:82)
	at org.gradle.internal.execution.impl.steps.CacheStep.execute(CacheStep.java:36)
	at org.gradle.internal.execution.impl.steps.PrepareCachingStep.execute(PrepareCachingStep.java:33)
	at org.gradle.internal.execution.impl.steps.StoreSnapshotsStep.execute(StoreSnapshotsStep.java:38)
	at org.gradle.internal.execution.impl.steps.StoreSnapshotsStep.execute(StoreSnapshotsStep.java:23)
	at org.gradle.internal.execution.impl.steps.SkipUpToDateStep.executeBecause(SkipUpToDateStep.java:96)
	at org.gradle.internal.execution.impl.steps.SkipUpToDateStep.lambda$execute$0(SkipUpToDateStep.java:89)
	at java.util.Optional.map(Optional.java:215)
	at org.gradle.internal.execution.impl.steps.SkipUpToDateStep.execute(SkipUpToDateStep.java:52)
	at org.gradle.internal.execution.impl.steps.SkipUpToDateStep.execute(SkipUpToDateStep.java:36)
	at org.gradle.internal.execution.impl.DefaultWorkExecutor.execute(DefaultWorkExecutor.java:34)
	at org.gradle.api.internal.tasks.execution.ExecuteActionsTaskExecuter.execute(ExecuteActionsTaskExecuter.java:91)
	at org.gradle.api.internal.tasks.execution.ResolveTaskOutputCachingStateExecuter.execute(ResolveTaskOutputCachingStateExecuter.java:91)
	at org.gradle.api.internal.tasks.execution.ValidatingTaskExecuter.execute(ValidatingTaskExecuter.java:57)
	at org.gradle.api.internal.tasks.execution.SkipEmptySourceFilesTaskExecuter.execute(SkipEmptySourceFilesTaskExecuter.java:119)
	at org.gradle.api.internal.tasks.execution.ResolvePreviousStateExecuter.execute(ResolvePreviousStateExecuter.java:43)
	at org.gradle.api.internal.tasks.execution.CleanupStaleOutputsExecuter.execute(CleanupStaleOutputsExecuter.java:93)
	at org.gradle.api.internal.tasks.execution.FinalizePropertiesTaskExecuter.execute(FinalizePropertiesTaskExecuter.java:45)
	at org.gradle.api.internal.tasks.execution.ResolveTaskArtifactStateTaskExecuter.execute(ResolveTaskArtifactStateTaskExecuter.java:94)
	at org.gradle.api.internal.tasks.execution.SkipTaskWithNoActionsExecuter.execute(SkipTaskWithNoActionsExecuter.java:56)
	at org.gradle.api.internal.tasks.execution.SkipOnlyIfTaskExecuter.execute(SkipOnlyIfTaskExecuter.java:55)
	at org.gradle.api.internal.tasks.execution.CatchExceptionTaskExecuter.execute(CatchExceptionTaskExecuter.java:36)
	at org.gradle.api.internal.tasks.execution.EventFiringTaskExecuter$1.executeTask(EventFiringTaskExecuter.java:67)
	at org.gradle.api.internal.tasks.execution.EventFiringTaskExecuter$1.call(EventFiringTaskExecuter.java:52)
	at org.gradle.api.internal.tasks.execution.EventFiringTaskExecuter$1.call(EventFiringTaskExecuter.java:49)
	at org.gradle.internal.operations.DefaultBuildOperationExecutor$CallableBuildOperationWorker.execute(DefaultBuildOperationExecutor.java:315)
	at org.gradle.internal.operations.DefaultBuildOperationExecutor$CallableBuildOperationWorker.execute(DefaultBuildOperationExecutor.java:305)
	at org.gradle.internal.operations.DefaultBuildOperationExecutor.execute(DefaultBuildOperationExecutor.java:175)
	at org.gradle.internal.operations.DefaultBuildOperationExecutor.call(DefaultBuildOperationExecutor.java:101)
	at org.gradle.internal.operations.DelegatingBuildOperationExecutor.call(DelegatingBuildOperationExecutor.java:36)
	at org.gradle.api.internal.tasks.execution.EventFiringTaskExecuter.execute(EventFiringTaskExecuter.java:49)
	at org.gradle.execution.plan.LocalTaskNodeExecutor.execute(LocalTaskNodeExecutor.java:43)
	at org.gradle.execution.taskgraph.DefaultTaskExecutionGraph$InvokeNodeExecutorsAction.execute(DefaultTaskExecutionGraph.java:355)
	at org.gradle.execution.taskgraph.DefaultTaskExecutionGraph$InvokeNodeExecutorsAction.execute(DefaultTaskExecutionGraph.java:343)
	at org.gradle.execution.taskgraph.DefaultTaskExecutionGraph$BuildOperationAwareExecutionAction.execute(DefaultTaskExecutionGraph.java:336)
	at org.gradle.execution.taskgraph.DefaultTaskExecutionGraph$BuildOperationAwareExecutionAction.execute(DefaultTaskExecutionGraph.java:322)
	at org.gradle.execution.plan.DefaultPlanExecutor$ExecutorWorker$1.execute(DefaultPlanExecutor.java:134)
	at org.gradle.execution.plan.DefaultPlanExecutor$ExecutorWorker$1.execute(DefaultPlanExecutor.java:129)
	at org.gradle.execution.plan.DefaultPlanExecutor$ExecutorWorker.execute(DefaultPlanExecutor.java:202)
	at org.gradle.execution.plan.DefaultPlanExecutor$ExecutorWorker.executeNextNode(DefaultPlanExecutor.java:193)
	at org.gradle.execution.plan.DefaultPlanExecutor$ExecutorWorker.run(DefaultPlanExecutor.java:129)
	at org.gradle.execution.plan.DefaultPlanExecutor.process(DefaultPlanExecutor.java:74)
	at org.gradle.execution.taskgraph.DefaultTaskExecutionGraph.executeWithServices(DefaultTaskExecutionGraph.java:178)
	at org.gradle.execution.taskgraph.DefaultTaskExecutionGraph.execute(DefaultTaskExecutionGraph.java:154)
	at org.gradle.execution.SelectedTaskExecutionAction.execute(SelectedTaskExecutionAction.java:41)
	at org.gradle.execution.DefaultBuildExecuter.execute(DefaultBuildExecuter.java:40)
	at org.gradle.execution.DefaultBuildExecuter.access$000(DefaultBuildExecuter.java:24)
	at org.gradle.execution.DefaultBuildExecuter$1.proceed(DefaultBuildExecuter.java:46)
	at org.gradle.execution.DryRunBuildExecutionAction.execute(DryRunBuildExecutionAction.java:49)
	at org.gradle.execution.DefaultBuildExecuter.execute(DefaultBuildExecuter.java:40)
	at org.gradle.execution.DefaultBuildExecuter.execute(DefaultBuildExecuter.java:33)
	at org.gradle.initialization.DefaultGradleLauncher$ExecuteTasks.run(DefaultGradleLauncher.java:383)
	at org.gradle.internal.operations.DefaultBuildOperationExecutor$RunnableBuildOperationWorker.execute(DefaultBuildOperationExecutor.java:301)
	at org.gradle.internal.operations.DefaultBuildOperationExecutor$RunnableBuildOperationWorker.execute(DefaultBuildOperationExecutor.java:293)
	at org.gradle.internal.operations.DefaultBuildOperationExecutor.execute(DefaultBuildOperationExecutor.java:175)
	at org.gradle.internal.operations.DefaultBuildOperationExecutor.run(DefaultBuildOperationExecutor.java:91)
	at org.gradle.internal.operations.DelegatingBuildOperationExecutor.run(DelegatingBuildOperationExecutor.java:31)
	at org.gradle.initialization.DefaultGradleLauncher.runTasks(DefaultGradleLauncher.java:247)
	at org.gradle.initialization.DefaultGradleLauncher.doBuildStages(DefaultGradleLauncher.java:159)
	at org.gradle.initialization.DefaultGradleLauncher.executeTasks(DefaultGradleLauncher.java:134)
	at org.gradle.internal.invocation.GradleBuildController$1.execute(GradleBuildController.java:58)
	at org.gradle.internal.invocation.GradleBuildController$1.execute(GradleBuildController.java:55)
	at org.gradle.internal.invocation.GradleBuildController$3.create(GradleBuildController.java:82)
	at org.gradle.internal.invocation.GradleBuildController$3.create(GradleBuildController.java:75)
	at org.gradle.internal.work.DefaultWorkerLeaseService.withLocks(DefaultWorkerLeaseService.java:183)
	at org.gradle.internal.work.StopShieldingWorkerLeaseService.withLocks(StopShieldingWorkerLeaseService.java:40)
	at org.gradle.internal.invocation.GradleBuildController.doBuild(GradleBuildController.java:75)
	at org.gradle.internal.invocation.GradleBuildController.run(GradleBuildController.java:55)
	at org.gradle.tooling.internal.provider.runner.ClientProvidedBuildActionRunner.run(ClientProvidedBuildActionRunner.java:55)
	at org.gradle.launcher.exec.ChainingBuildActionRunner.run(ChainingBuildActionRunner.java:35)
	at org.gradle.launcher.exec.ChainingBuildActionRunner.run(ChainingBuildActionRunner.java:35)
	at org.gradle.launcher.exec.BuildOutcomeReportingBuildActionRunner.run(BuildOutcomeReportingBuildActionRunner.java:58)
	at org.gradle.tooling.internal.provider.ValidatingBuildActionRunner.run(ValidatingBuildActionRunner.java:32)
	at org.gradle.launcher.exec.BuildCompletionNotifyingBuildActionRunner.run(BuildCompletionNotifyingBuildActionRunner.java:39)
	at org.gradle.launcher.exec.RunAsBuildOperationBuildActionRunner$3.call(RunAsBuildOperationBuildActionRunner.java:49)
	at org.gradle.launcher.exec.RunAsBuildOperationBuildActionRunner$3.call(RunAsBuildOperationBuildActionRunner.java:44)
	at org.gradle.internal.operations.DefaultBuildOperationExecutor$CallableBuildOperationWorker.execute(DefaultBuildOperationExecutor.java:315)
	at org.gradle.internal.operations.DefaultBuildOperationExecutor$CallableBuildOperationWorker.execute(DefaultBuildOperationExecutor.java:305)
	at org.gradle.internal.operations.DefaultBuildOperationExecutor.execute(DefaultBuildOperationExecutor.java:175)
	at org.gradle.internal.operations.DefaultBuildOperationExecutor.call(DefaultBuildOperationExecutor.java:101)
	at org.gradle.internal.operations.DelegatingBuildOperationExecutor.call(DelegatingBuildOperationExecutor.java:36)
	at org.gradle.launcher.exec.RunAsBuildOperationBuildActionRunner.run(RunAsBuildOperationBuildActionRunner.java:44)
	at org.gradle.launcher.exec.InProcessBuildActionExecuter$1.transform(InProcessBuildActionExecuter.java:49)
	at org.gradle.launcher.exec.InProcessBuildActionExecuter$1.transform(InProcessBuildActionExecuter.java:46)
	at org.gradle.composite.internal.DefaultRootBuildState.run(DefaultRootBuildState.java:78)
	at org.gradle.launcher.exec.InProcessBuildActionExecuter.execute(InProcessBuildActionExecuter.java:46)
	at org.gradle.launcher.exec.InProcessBuildActionExecuter.execute(InProcessBuildActionExecuter.java:31)
	at org.gradle.launcher.exec.BuildTreeScopeBuildActionExecuter.execute(BuildTreeScopeBuildActionExecuter.java:42)
	at org.gradle.launcher.exec.BuildTreeScopeBuildActionExecuter.execute(BuildTreeScopeBuildActionExecuter.java:28)
	at org.gradle.tooling.internal.provider.ContinuousBuildActionExecuter.execute(ContinuousBuildActionExecuter.java:78)
	at org.gradle.tooling.internal.provider.ContinuousBuildActionExecuter.execute(ContinuousBuildActionExecuter.java:52)
	at org.gradle.tooling.internal.provider.SubscribableBuildActionExecuter.execute(SubscribableBuildActionExecuter.java:59)
	at org.gradle.tooling.internal.provider.SubscribableBuildActionExecuter.execute(SubscribableBuildActionExecuter.java:36)
	at org.gradle.tooling.internal.provider.SessionScopeBuildActionExecuter.execute(SessionScopeBuildActionExecuter.java:68)
	at org.gradle.tooling.internal.provider.SessionScopeBuildActionExecuter.execute(SessionScopeBuildActionExecuter.java:38)
	at org.gradle.tooling.internal.provider.GradleThreadBuildActionExecuter.execute(GradleThreadBuildActionExecuter.java:37)
	at org.gradle.tooling.internal.provider.GradleThreadBuildActionExecuter.execute(GradleThreadBuildActionExecuter.java:26)
	at org.gradle.tooling.internal.provider.ParallelismConfigurationBuildActionExecuter.execute(ParallelismConfigurationBuildActionExecuter.java:43)
	at org.gradle.tooling.internal.provider.ParallelismConfigurationBuildActionExecuter.execute(ParallelismConfigurationBuildActionExecuter.java:29)
	at org.gradle.tooling.internal.provider.StartParamsValidatingActionExecuter.execute(StartParamsValidatingActionExecuter.java:60)
	at org.gradle.tooling.internal.provider.StartParamsValidatingActionExecuter.execute(StartParamsValidatingActionExecuter.java:32)
	at org.gradle.tooling.internal.provider.SessionFailureReportingActionExecuter.execute(SessionFailureReportingActionExecuter.java:55)
	at org.gradle.tooling.internal.provider.SessionFailureReportingActionExecuter.execute(SessionFailureReportingActionExecuter.java:41)
	at org.gradle.tooling.internal.provider.SetupLoggingActionExecuter.execute(SetupLoggingActionExecuter.java:48)
	at org.gradle.tooling.internal.provider.SetupLoggingActionExecuter.execute(SetupLoggingActionExecuter.java:32)
	at org.gradle.launcher.daemon.server.exec.ExecuteBuild.doBuild(ExecuteBuild.java:67)
	at org.gradle.launcher.daemon.server.exec.BuildCommandOnly.execute(BuildCommandOnly.java:36)
	at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:104)
	at org.gradle.launcher.daemon.server.exec.WatchForDisconnection.execute(WatchForDisconnection.java:37)
	at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:104)
	at org.gradle.launcher.daemon.server.exec.ResetDeprecationLogger.execute(ResetDeprecationLogger.java:26)
	at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:104)
	at org.gradle.launcher.daemon.server.exec.RequestStopIfSingleUsedDaemon.execute(RequestStopIfSingleUsedDaemon.java:34)
	at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:104)
	at org.gradle.launcher.daemon.server.exec.ForwardClientInput$2.call(ForwardClientInput.java:74)
	at org.gradle.launcher.daemon.server.exec.ForwardClientInput$2.call(ForwardClientInput.java:72)
	at org.gradle.util.Swapper.swap(Swapper.java:38)
	at org.gradle.launcher.daemon.server.exec.ForwardClientInput.execute(ForwardClientInput.java:72)
	at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:104)
	at org.gradle.launcher.daemon.server.exec.LogAndCheckHealth.execute(LogAndCheckHealth.java:55)
	at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:104)
	at org.gradle.launcher.daemon.server.exec.LogToClient.doBuild(LogToClient.java:62)
	at org.gradle.launcher.daemon.server.exec.BuildCommandOnly.execute(BuildCommandOnly.java:36)
	at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:104)
	at org.gradle.launcher.daemon.server.exec.EstablishBuildEnvironment.doBuild(EstablishBuildEnvironment.java:81)
	at org.gradle.launcher.daemon.server.exec.BuildCommandOnly.execute(BuildCommandOnly.java:36)
	at org.gradle.launcher.daemon.server.api.DaemonCommandExecution.proceed(DaemonCommandExecution.java:104)
	at org.gradle.launcher.daemon.server.exec.StartBuildOrRespondWithBusy$1.run(StartBuildOrRespondWithBusy.java:50)
	at org.gradle.launcher.daemon.server.DaemonStateCoordinator$1.run(DaemonStateCoordinator.java:295)
	at org.gradle.internal.concurrent.ExecutorPolicy$CatchAndRecordFailures.onExecute(ExecutorPolicy.java:63)
	at org.gradle.internal.concurrent.ManagedExecutorImpl$1.run(ManagedExecutorImpl.java:46)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1142)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:617)
	at org.gradle.internal.concurrent.ThreadFactoryImpl$ManagedThreadRunnable.run(ThreadFactoryImpl.java:55)
	at java.lang.Thread.run(Thread.java:745)
	at com.android.build.gradle.internal.transforms.DexArchiveBuilderTransform.launchProcessing(DexArchiveBuilderTransform.java:909)
	at com.android.build.gradle.internal.transforms.DexArchiveBuilderTransform.lambda$convertToDexArchive$6(DexArchiveBuilderTransform.java:834)
	at java.util.concurrent.ForkJoinTask$AdaptedCallable.exec(ForkJoinTask.java:1424)
	at java.util.concurrent.ForkJoinTask.doExec(ForkJoinTask.java:289)
	at java.util.concurrent.ForkJoinPool$WorkQueue.runTask(ForkJoinPool.java:1056)
	at java.util.concurrent.ForkJoinPool.runWorker(ForkJoinPool.java:1692)
	at java.util.concurrent.ForkJoinWorkerThread.run(ForkJoinWorkerThread.java:157)
	at com.android.builder.dexing.D8DexArchiveBuilder.getExceptionToRethrow(D8DexArchiveBuilder.java:124)
	at com.android.builder.dexing.D8DexArchiveBuilder.convert(D8DexArchiveBuilder.java:101)
	at com.android.build.gradle.internal.transforms.DexArchiveBuilderTransform.launchProcessing(DexArchiveBuilderTransform.java:904)
	... 6 more
	at com.android.tools.r8.utils.ExceptionUtils.withCompilationHandler(ExceptionUtils.java:81)
	at com.android.tools.r8.utils.ExceptionUtils.withD8CompilationHandler(ExceptionUtils.java:45)
	at com.android.tools.r8.D8.run(D8.java:94)
	at com.android.builder.dexing.D8DexArchiveBuilder.convert(D8DexArchiveBuilder.java:99)
	... 7 more
	at com.android.tools.r8.utils.Reporter.failIfPendingErrors(Reporter.java:101)
	at com.android.tools.r8.utils.Reporter.fatalError(Reporter.java:72)
	at com.android.tools.r8.utils.ExceptionUtils.withCompilationHandler(ExceptionUtils.java:66)
	... 10 more
> Task :app:transformClassesWithDexBuilderForDebug FAILED
> Task :app:buildInfoGeneratorDebug
FAILURE: Build failed with an exception.
* What went wrong:
Execution failed for task ':app:transformClassesWithDexBuilderForDebug'.
> com.android.build.api.transform.TransformException: com.android.builder.dexing.DexArchiveBuilderException: com.android.builder.dexing.DexArchiveBuilderException: Failed to process /home/mkh/.gradle/caches/transforms-2/files-2.1/269996e901f644d75b755f38d6670581/jars/classes.jar
~~~~~

Previous release of library does not have the problem
-----------------------------------------------------

Change the library to `androidx.core:core-ktx:1.2.0-alpha01` and the problem goes away.

Change the library to `androidx.core:core-ktx:1.2.0-alpha02` and the problem goes away.

Links
-----

GitHub: <https://github.com/hanafey/ktx-alpha02.git>
