---
title: "How to: Specify Verbose Log Files for ClickOnce Deployments"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - VB
  - CSharp
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - vs-ide-deployment
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 0807a28d-2e40-4a51-ab10-308d808ded6b
caps.latest.revision: 9
manager: wpickett
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pl-pl
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
---
# How to: Specify Verbose Log Files for ClickOnce Deployments
ClickOnce maintains activity log files for all deployments. These logs document details pertaining to installing, initializing, updating, and uninstalling a ClickOnce deployment. To increase the detail that ClickOnce writes to these log files, use Registry Editor (**regedit.exe**) to specify the verbosity level.  
  
> [!CAUTION]
>  If you use Registry Editor incorrectly, you may cause serious problems that may require you to reinstall the operating system. Use Registry Editor at your own risk.  
  
 The following procedure describes how to specify the verbosity level for ClickOnce log files for the current user. To reduce the level of verbosity, remove this registry value.  
  
### To specify verbose log files  
  
1.  Open **Regedit.exe**.  
  
2.  Navigate to the node `HKEY_CURRENT_USER\Software\Classes\Software\Microsoft\Windows\CurrentVersion\Deployment`.  
  
3.  If necessary, create a new string value named `LogVerbosityLevel`.  
  
4.  Set the `LogVerbosityLevel` value to `1`.  
  
## See Also  
 [Troubleshooting ClickOnce Deployments](../VS_IDE/Troubleshooting-ClickOnce-Deployments.md)