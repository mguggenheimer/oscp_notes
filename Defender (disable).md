```Bash
Set-MpPrefernce -DisableIntrusionPreventionSystem $true -DisableRealtimeMonitoring $true -DisableScriptScanning $true -EnableControlledFolderAccess Disabled -EnableNetworkProtection AuditMode -force -MAPSReporting Disabled -SubmitSamplesConsent NeverSend
```