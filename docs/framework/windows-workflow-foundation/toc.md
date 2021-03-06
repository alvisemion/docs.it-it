# [Windows Workflow Foundation](index.md)
## [Guida alla documentazione dei flussi di lavoro di Windows](guide-to-the-documentation.md)
## [Novità in Windows Workflow Foundation](whats-new.md)
## [Novità in Windows Workflow Foundation in .NET 4.5](whats-new-in-wf-in-dotnet.md)
## [Tipi deprecati in Windows Workflow Foundation](deprecated-types.md)
## [Specifiche delle funzionalità di Windows Workflow Foundation](feature-specifics.md)
## [Panoramica dei concetti relativi al flusso di lavoro di Windows](conceptual-overview.md)
### [Panoramica del flusso di lavoro di Windows](overview.md)
### [Concetti di base del flusso di lavoro di Windows](fundamental-concepts.md)
### [Architettura del flusso di lavoro di Windows](architecture.md)
## [Esercitazione introduttiva](getting-started-tutorial.md)
### [Procedura: Creare un'attività](how-to-create-an-activity.md)
### [Procedura: Creare un flusso di lavoro](how-to-create-a-workflow.md)
#### [Procedura: Creare un flusso di lavoro del diagramma di flusso](how-to-create-a-flowchart-workflow.md)
#### [Procedura: Creare un flusso di lavoro sequenziale](how-to-create-a-sequential-workflow.md)
#### [Procedura: Creare un flusso di lavoro della macchina a stati](how-to-create-a-state-machine-workflow.md)
### [Procedura: Eseguire un flusso di lavoro](how-to-run-a-workflow.md)
### [Procedura: Creare ed eseguire un flusso di lavoro con esecuzione prolungata](how-to-create-and-run-a-long-running-workflow.md)
### [Procedura: Creare un partecipante di rilevamento personalizzato](how-to-create-a-custom-tracking-participant.md)
### [Procedura: Ospitare più versioni di un flusso di lavoro side-by-side](how-to-host-multiple-versions-of-a-workflow-side-by-side.md)
### [Procedura: Aggiornare la definizione di un'istanza del flusso di lavoro in esecuzione](how-to-update-the-definition-of-a-running-workflow-instance.md)
## [Programmazione di Windows Workflow Foundation](programming.md)
### [Progettazione di flussi di lavoro](designing-workflows.md)
#### [Flussi di lavoro del diagramma di flusso](flowchart-workflows.md)
#### [Flussi di lavoro procedurali](procedural-workflows.md)
#### [Flussi di lavoro della macchina a stati](state-machine-workflows.md)
#### [Creazione di flussi di lavoro, attività ed espressioni tramite codice imperativo](authoring-workflows-activities-and-expressions-using-imperative-code.md)
### [Uso e creazione di attività](using-and-creating-activities.md)
#### [Libreria di attività incorporata](net-framework-4-5-built-in-activity-library.md)
##### [Flusso di controllo](control-flow-activities-in-wf.md)
###### [Attività di selezione](pick-activity.md)
##### [Diagramma di flusso](flowchart-activities-in-wf.md)
##### [Macchina a stati](state-machine-activities-in-wf.md)
##### [Runtime](runtime-activities-in-wf.md)
##### [Primitive](primitives-activities-in-wf.md)
##### [Transazione](transaction-activities-in-wf.md)
##### [Raccolta](collection-activities-in-wf.md)
##### [Gestione degli errori](error-handling-activities-in-wf.md)
##### [Migrazione](migration-activity-in-wf.md)
#### [Progettazione e implementazione di attività personalizzate](designing-and-implementing-custom-activities.md)
##### [Opzioni di creazione di attività](activity-authoring-options-in-wf.md)
###### [Classe di base di attività](workflow-activity-authoring-using-the-activity-class.md)
###### [Classe di base CodeActivity](workflow-activity-authoring-using-the-codeactivity-class.md)
###### [Classe di base NativeActivity](nativeactivity-base-class.md)
##### [Uso di un'attività personalizzata](using-a-custom-activity.md)
##### [Creazione di attività asincrone](creating-asynchronous-activities-in-wf.md)
###### [Gestione degli errori in attività asincrone](error-handling-in-asynchronous-activities.md)
##### [Configurazione della convalida di attività](configuring-activity-validation.md)
###### [Argomenti obbligatori e gruppi di overload](required-arguments-and-overload-groups.md)
###### [Convalida basata su codice imperativo](imperative-code-based-validation.md)
###### [Vincoli dichiarativi](declarative-constraints.md)
###### [Richiamo della convalida di attività](invoking-activity-validation.md)
##### [Creazione di un'attività in fase di esecuzione](creating-an-activity-at-runtime-with-dynamicactivity.md)
##### [Proprietà di esecuzione del flusso di lavoro](workflow-execution-properties.md)
##### [Uso di delegati di attività](using-activity-delegates.md)
##### [Localizzazione di attività](activity-localization.md)
##### [Uso di estensioni di attività](using-activity-extensions.md)
##### [Utilizzo di feed OData da un flusso di lavoro](consuming-odata-feeds-from-a-workflow.md)
##### [Ambito e visibilità della definizione di attività](activity-definition-scoping-and-visibility.md)
##### [Creazione di attività di controllo del flusso personalizzate](creating-custom-flow-control-activities.md)
### [Modello di dati di Windows Workflow Foundation](data-model.md)
#### [Variabili e argomenti](variables-and-arguments.md)
#### [Espressioni](expressions.md)
#### [Espressioni C#](csharp-expressions.md)
#### [Proprietà e argomenti](properties-vs-arguments.md)
#### [Esposizione dei dati con CacheMetadata](exposing-data-with-cachemetadata.md)
### [Attesa per l'input in un flusso di lavoro](waiting-for-input-in-a-workflow.md)
#### [Segnalibri](bookmarks.md)
### [Eccezioni, transazioni e compensazione](exceptions-transactions-and-compensation.md)
#### [Eccezioni](exceptions.md)
#### [Transazioni](workflow-transactions.md)
#### [Compensazione](compensation.md)
#### [Annullamento](modeling-cancellation-behavior-in-workflows.md)
#### [Esecuzione del debug dei flussi di lavoro](debugging-workflows.md)
### [Hosting dei flussi di lavoro](hosting-workflows.md)
#### [Opzioni di hosting dei flussi di lavoro](workflow-hosting-options.md)
#### [Uso di WorkflowInvoker e WorkflowApplication](using-workflowinvoker-and-workflowapplication.md)
#### [Ispezione dell'albero delle attività](activity-tree-inspection.md)
#### [Serializzazione di flussi di lavoro e attività da e verso XAML](serializing-workflows-and-activities-to-and-from-xaml.md)
#### [Uso di WorkflowIdentity e controllo delle versioni](using-workflowidentity-and-versioning.md)
### [Aggiornamento dinamico](dynamic-update.md)
### [Sviluppo del servizio del flusso di lavoro con priorità al contratto ("contract-first")](contract-first-workflow-service-development.md)
### [Procedura: Creare un servizio di flusso di lavoro che utilizza un contratto di servizio esistente](how-to-create-a-workflow-service-that-consumes-an-existing-service-contract.md)
### [Persistenza del flusso di lavoro](workflow-persistence.md)
#### [Archivio di istanze del flusso di lavoro SQL](sql-workflow-instance-store.md)
##### [Proprietà dell'archivio di istanze del flusso di lavoro SQL](properties-of-sql-workflow-instance-store.md)
###### [Instance Encoding Option](instance-encoding-option.md)
###### [Instance Completion Action](instance-completion-action.md)
###### [Instance Locked Exception Action](instance-locked-exception-action.md)
###### [Host Lock Renewal Period](host-lock-renewal-period.md)
###### [Runnable Instances Detection Period](runnable-instances-detection-period.md)
###### [Connection String e Connection String Name](connection-string-and-connection-string-name.md)
##### [Procedura: Abilitare la persistenza SQL per i flussi di lavoro e i relativi servizi](how-to-enable-sql-persistence-for-workflows-and-workflow-services.md)
##### [Attivazione di istanze](instance-activation.md)
##### [Supporto per le query](support-for-queries.md)
##### [Estendibilità dell'archivio](store-extensibility.md)
##### [Sicurezza](security.md)
##### [Database di persistenza di SQL Server](sql-server-persistence-database.md)
###### [Schema del database di persistenza](persistence-database-schema.md)
###### [Procedura: Deserializzare le proprietà dei dati dell'istanza](how-to-deserialize-instance-data-properties.md)
###### [Procedura: Eseguire query per istanze non persistenti](how-to-query-for-non-persisted-instances.md)
#### [Archivi di istanze](instance-stores.md)
##### [Procedura: Abilitare la persistenza per i flussi di lavoro e i relativi servizi](how-to-enable-persistence-for-workflows-and-workflow-services.md)
##### [Procedura: Creare un archivio di istanze personalizzato](how-to-create-a-custom-instance-store.md)
#### [Partecipanti di persistenza](persistence-participants.md)
##### [Procedura: Creare un partecipante di persistenza personalizzato](how-to-create-a-custom-persistence-participant.md)
#### [Procedure consigliate per la persistenza](persistence-best-practices.md)
#### [Istanze del flusso di lavoro non persistenti](non-persisted-workflow-instances.md)
#### [Sospensione e ripresa di un flusso di lavoro](pausing-and-resuming-a-workflow.md)
### [Materiale sussidiario di migrazione](wf-migration-guidance.md)
#### [Materiale sussidiario di migrazione](migration-guidance.md)
#### [Uso delle attività WF di .NET Framework 3.0 in .NET Framework 4 con l'attività di interoperabilità](net-framework-3-0-wf-in-net-framework-4-interop.md)
#### [Uso dell'attività di interoperabilità in un flusso di lavoro di .NET Framework 4](using-the-interop-activity-in-a-net-framework-4-workflow.md)
#### [Scrittura di progetti destinati a .NET Framework 3.0 e 3.5 in Visual Studio 2010](projects-targeting-dotnet-in-vs.md)
### [Rilevamento e analisi del flusso di lavoro](workflow-tracking-and-tracing.md)
#### [Record di rilevamento](tracking-records.md)
#### [Profili di rilevamento](tracking-profiles.md)
#### [Partecipanti di rilevamento](tracking-participants.md)
#### [Configurazione del rilevamento per un flusso di lavoro](configuring-tracking-for-a-workflow.md)
#### [Uso del rilevamento per la risoluzione dei problemi relativi alle applicazioni](using-tracking-to-troubleshoot-applications.md)
#### [Analisi del flusso di lavoro](workflow-tracing.md)
#### [Riferimento agli eventi di rilevamento](tracking-events-reference.md)
##### [100 - WorkflowInstanceRecord](100-workflowinstancerecord.md)
##### [101 - WorkflowInstanceUnhandledExceptionRecord](101-workflowinstanceunhandledexceptionrecord.md)
##### [102 - WorkflowInstanceAbortedRecord](102-workflowinstanceabortedrecord.md)
##### [103 - ActivityStateRecord](103-activitystaterecord.md)
##### [104 - ActivityScheduledRecord](104-activityscheduledrecord.md)
##### [105 - FaultPropagationRecord](105-faultpropagationrecord.md)
##### [106 - CancelRequestRecord](106-cancelrequestrecord.md)
##### [107 -- BookmarkResumptionRecord](107-bookmarkresumptionrecord.md)
##### [108 - CustomTrackingRecordInfo](108-customtrackingrecordinfo.md)
##### [110 - CustomTrackingRecordWarning](110-customtrackingrecordwarning.md)
##### [111 - CustomTrackingRecordError](111-customtrackingrecorderror.md)
##### [112 - WorkflowInstanceSuspendedRecord](112-workflowinstancesuspendedrecord.md)
##### [113 - WorkflowInstanceTerminatedRecord](113-workflowinstanceterminatedrecord.md)
##### [114 - WorkflowInstanceRecordWithId](114-workflowinstancerecordwithid.md)
##### [115 - WorkflowInstanceAbortedRecordWithId](115-workflowinstanceabortedrecordwithid.md)
##### [116 - WorkflowInstanceSuspendedRecordWithId](116-workflowinstancesuspendedrecordwithid.md)
##### [117 - WorkflowInstanceTerminatedRecordWithId](117-workflowinstanceterminatedrecordwithid.md)
##### [118 - WorkflowInstanceUnhandledExceptionRecordWithId](118-workflowinstanceunhandledexceptionrecordwithid.md)
##### [119 - WorkflowInstanceUpdatedRecord](119-workflowinstanceupdatedrecord.md)
##### [225 - TraceCorrelationKeys](225-tracecorrelationkeys.md)
##### [440 - StartSignpostEvent1](440-startsignpostevent.md)
##### [441- StopSignpostEvent1](441-stopsignpostevent.md)
##### [1001 - WorkflowApplicationCompleted](1001-workflowapplicationcompleted.md)
##### [1002 - WorkflowApplicationTerminated](1002-workflowapplicationterminated.md)
##### [1003 - WorkflowInstanceCanceled](1003-workflowinstancecanceled.md)
##### [1004 - WorkflowInstanceAborted](1004-workflowinstanceaborted.md)
##### [1005 - WorkflowApplicationIdled](1005-workflowapplicationidled.md)
##### [1006 - WorkflowApplicationUnhandledException](1006-workflowapplicationunhandledexception.md)
##### [1007 - WorkflowApplicationPersisted](1007-workflowapplicationpersisted.md)
##### [1008 - WorkflowApplicationUnloaded](1008-workflowapplicationunloaded.md)
##### [1009 - ActivityScheduled](1009-activityscheduled.md)
##### [1010 - ActivityCompleted](1010-activitycompleted.md)
##### [1011 - ScheduleExecuteActivityWorkItem](1011-scheduleexecuteactivityworkitem.md)
##### [1012 - StartExecuteActivityWorkItem](1012-startexecuteactivityworkitem.md)
##### [1013 - CompleteExecuteActivityWorkItem](1013-completeexecuteactivityworkitem.md)
##### [1014 - ScheduleCompletionWorkItem](1014-schedulecompletionworkitem.md)
##### [1015 - StartCompletionWorkItem](1015-startcompletionworkitem.md)
##### [1016 - CompleteCompletionWorkItem](1016-completecompletionworkitem.md)
##### [1017 - ScheduleCancelActivityWorkItem](1017-schedulecancelactivityworkitem.md)
##### [1018 - StartCancelActivityWorkItem](1018-startcancelactivityworkitem.md)
##### [1019 - CompleteCancelActivityWorkItem](1019-completecancelactivityworkitem.md)
##### [1020 - CreateBookmark](1020-createbookmark.md)
##### [1021 - ScheduleBookmarkWorkItem](1021-schedulebookmarkworkitem.md)
##### [1022 - StartBookmarkWorkItem](1022-startbookmarkworkitem.md)
##### [1023 - CompleteBookmarkWorkItem](1023-completebookmarkworkitem.md)
##### [1024 - CreateBookmarkScope](1024-createbookmarkscope.md)
##### [1025 - BookmarkScopeInitialized](1025-bookmarkscopeinitialized.md)
##### [1026 - ScheduleTransactionContextWorkItem](1026-scheduletransactioncontextworkitem.md)
##### [1027 - StartTransactionContextWorkItem](1027-starttransactioncontextworkitem.md)
##### [1028 - CompleteTransactionContextWorkItem](1028-completetransactioncontextworkitem.md)
##### [1029 - ScheduleFaultWorkItem](1029-schedulefaultworkitem.md)
##### [1030 - StartFaultWorkItem](1030-startfaultworkitem.md)
##### [1031 - CompleteFaultWorkItem](1031-completefaultworkitem.md)
##### [1032 - ScheduleRuntimeWorkItem](1032-scheduleruntimeworkitem.md)
##### [1033 - StartRuntimeWorkItem](1033-startruntimeworkitem.md)
##### [1034 - CompleteRuntimeWorkItem](1034-completeruntimeworkitem.md)
##### [1035 - RuntimeTransactionSet](1035-runtimetransactionset.md)
##### [1036 - RuntimeTransactionCompletionRequested](1036-runtimetransactioncompletionrequested.md)
##### [1037 - RuntimeTransactionComplete](1037-runtimetransactioncomplete.md)
##### [1038 - EnterNoPersistBlock](1038-enternopersistblock.md)
##### [1039 - ExitNoPersistBlock](1039-exitnopersistblock.md)
##### [1040 - InArgumentBound](1040-inargumentbound.md)
##### [1041 - WorkflowApplicationPersistableIdle](1041-workflowapplicationpersistableidle.md)
##### [1101 - WorkflowActivityStart](1101-workflowactivitystart.md)
##### [1102 - WorkflowActivityStop](1102-workflowactivitystop.md)
##### [1103 - WorkflowActivitySuspend](1103-workflowactivitysuspend.md)
##### [1104 - WorkflowActivityResume](1104-workflowactivityresume.md)
##### [1124 - InvokeMethodIsStatic](1124-invokemethodisstatic.md)
##### [1125 - InvokeMethodIsNotStatic](1125-invokemethodisnotstatic.md)
##### [1126 - InvokedMethodThrewException](1126-invokedmethodthrewexception.md)
##### [1131 - InvokeMethodUseAsyncPattern](1131-invokemethoduseasyncpattern.md)
##### [1132 - InvokeMethodDoesNotUseAsyncPattern](1132-invokemethoddoesnotuseasyncpattern.md)
##### [1140 - FlowchartStart](1140-flowchartstart.md)
##### [1141 - FlowchartEmpty](1141-flowchartempty.md)
##### [1143 - FlowchartNextNull](1143-flowchartnextnull.md)
##### [1146 - FlowchartSwitchCase](1146-flowchartswitchcase.md)
##### [1147 - FlowchartSwitchDefault](1147-flowchartswitchdefault.md)
##### [1148 - FlowchartSwitchCaseNotFound](1148-flowchartswitchcasenotfound.md)
##### [1150 - CompensationState](1150-compensationstate.md)
##### [1223 - SwitchCaseNotFound](1223-switchcasenotfound.md)
##### [1449 - WfMessageReceived](1449-wfmessagereceived.md)
##### [1450 - WfMessageSent](1450-wfmessagesent.md)
##### [2021 - ExecuteWorkItemStart](2021-executeworkitemstart.md)
##### [2022 - ExecuteWorkItemStop](2022-executeworkitemstop.md)
##### [2023 - SendMessageChannelCacheMiss](2023-sendmessagechannelcachemiss.md)
##### [2024 - InternalCacheMetadataStart](2024-internalcachemetadatastart.md)
##### [2025 - InternalCacheMetadataStop](2025-internalcachemetadatastop.md)
##### [2026 - CompileVbExpressionStart](2026-compilevbexpressionstart.md)
##### [2027 - CacheRootMetadataStart](2027-cacherootmetadatastart.md)
##### [2028 - CacheRootMetadataStop](2028-cacherootmetadatastop.md)
##### [2029 - CompileVbExpressionStop](2029-compilevbexpressionstop.md)
##### [2576 - TryCatchExceptionFromTry](2576-trycatchexceptionfromtry.md)
##### [2577 - TryCatchExceptionDuringCancelation](2577-trycatchexceptionduringcancelation.md)
##### [2578 - TryCatchExceptionFromCatchOrFinally](2578-trycatchexceptionfromcatchorfinally.md)
##### [3501 - InferredContractDescription](3501-inferredcontractdescription.md)
##### [3502 - InferredOperationDescription](3502-inferredoperationdescription.md)
##### [3503 - DuplicateCorrelationQuery](3503-duplicatecorrelationquery.md)
##### [3507 - ServiceEndpointAdded](3507-serviceendpointadded.md)
##### [3508 - TrackingProfileNotFound](3508-trackingprofilenotfound.md)
##### [3550 - BufferOutOfOrderMessageNoInstance](3550-bufferoutofordermessagenoinstance.md)
##### [3551 - BufferOutOfOrderMessageNoBookmark](3551-bufferoutofordermessagenobookmark.md)
##### [3552 - MaxPendingMessagesPerChannelExceeded](3552-maxpendingmessagesperchannelexceeded.md)
##### [3557 - TransactedReceiveScopeEndCommitFailed](3557-transactedreceivescopeendcommitfailed.md)
##### [4201 - EndSqlCommandExecute](4201-endsqlcommandexecute.md)
##### [4202 - StartSqlCommandExecute](4202-startsqlcommandexecute.md)
##### [4203 - RenewLockSystemError](4203-renewlocksystemerror.md)
##### [4205 - FoundProcessingError](4205-foundprocessingerror.md)
##### [4206 - UnlockInstanceException](4206-unlockinstanceexception.md)
##### [4207 - MaximumRetriesExceededForSqlCommand](4207-maximumretriesexceededforsqlcommand.md)
##### [4208 - RetryingSqlCommandDueToSqlError](4208-retryingsqlcommandduetosqlerror.md)
##### [4209 - TimeoutOpeningSqlConnection](4209-timeoutopeningsqlconnection.md)
##### [4210 - SqlExceptionCaught](4210-sqlexceptioncaught.md)
##### [4211 - QueuingSqlRetry](4211-queuingsqlretry.md)
##### [4212 - LockRetryTimeout](4212-lockretrytimeout.md)
##### [4213 - RunnableInstancesDetectionError](4213-runnableinstancesdetectionerror.md)
##### [4214 - InstanceLocksRecoveryError](4214-instancelocksrecoveryerror.md)
##### [39456 - TrackingRecordDropped](39456-trackingrecorddropped.md)
##### [39457 - TrackingRecordRaised](39457-trackingrecordraised.md)
##### [39458 - TrackingRecordTruncated](39458-trackingrecordtruncated.md)
##### [39459 - TrackingDataExtracted](39459-trackingdataextracted.md)
##### [39460 - TrackingValueNotSerializable](39460-trackingvaluenotserializable.md)
##### [57398 - MaxInstancesExceeded](57398-maxinstancesexceeded.md)
#### [Record di rilevamento personalizzati](custom-tracking-records.md)
#### [Rilevamento di variabili e argomenti](variable-and-argument-tracking.md)
#### [Determinazione della durata di esecuzione del flusso di lavoro tramite analisi](determining-workflow-execution-duration-using-tracing.md)
### [Sicurezza del flusso di lavoro](workflow-security.md)
### [Prestazioni di Windows Workflow Foundation 4](performance.md)
## [Estensione di Windows Workflow Foundation](extend.md)
### [Personalizzazione della fase di progettazione del flusso di lavoro](customizing-the-workflow-design-experience.md)
#### [Uso di finestre di progettazione e modelli di attività personalizzati](using-custom-activity-designers-and-templates.md)
##### [Procedura: Creare una finestra di progettazione di attività personalizzata](how-to-create-a-custom-activity-designer.md)
##### [Procedura: Creare un modello di attività personalizzato](how-to-create-a-custom-activity-template.md)
##### [Uso del contesto di modifica ModelItem](using-the-modelitem-editing-context.md)
##### [Associazione di una proprietà di attività personalizzata a un controllo di progettazione](binding-a-custom-activity-property-to-a-designer-control.md)
#### [Riallocazione di Progettazione flussi di lavoro](rehosting-the-workflow-designer.md)
##### [Attività 1: Creare una nuova applicazione Windows Presentation Foundation](task-1-create-a-new-wpf-app.md)
##### [Attività 2: Ospitare Progettazione flussi di lavoro](task-2-host-the-workflow-designer.md)
##### [Attività 3: Creare i riquadri Casella degli strumenti e PropertyGrid](task-3-create-the-toolbox-and-propertygrid-panes.md)
##### [Procedura: Visualizzare errori di convalida in una finestra di progettazione riallocata](how-to-display-validation-errors-in-a-rehosted-designer.md)
##### [Supporto delle nuove funzionalità di Workflow Foundation 4.5 in Progettazione flussi di lavoro riallocato](wf-features-in-the-rehosted-workflow-designer.md)
#### [Uso di un editor di espressioni personalizzato](using-a-custom-expression-editor.md)
## [Glossario di Windows Workflow Foundation](glossary.md)
## [Esempi di flussi di lavoro di Windows](samples/)
