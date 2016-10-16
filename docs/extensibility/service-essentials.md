---
title: "Service Essentials"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: na
ms.topic: "article"
helpviewer_keywords: 
  - "services, essentials"
ms.assetid: fbe84ad9-efe1-48b1-aba3-b50b90424d47
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
translation.priority.mt: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# Service Essentials
A service is a contract between two VSPackages. One VSPackage provides a specific set of interfaces for another VSPackage to consume. [!INCLUDE[vsprvs](../codequality/includes/vsprvs_md.md)] is itself a collection of VSPackages that provides services to other VSPackages.  
  
 For example, you can use the SVsActivityLog service to obtain an IVsActivityLog interface, which you can use to write to the activity log. For more information, see [How to: Use the Activity Log](../extensibility/how-to--use-the-activity-log.md).  
  
 [!INCLUDE[vsprvs](../codequality/includes/vsprvs_md.md)] also provides some built-in services which are not registered. VSPackages can replace built-in or other services by providing a service override. Only one service override is permitted for any service.  
  
 Services have no discoverability. Therefore, you must know the service identifier (SID) of a service that you want to consume, and you must know which interfaces it provides. The reference documentation for the service provides this information.  
  
-   VSPackages that provide services are called service providers.  
  
-   Services that are provided to other VSPackages are called global services.  
  
-   Services that are available only to the VSPackage that implements them, or to any object it creates, are called local services.  
  
-   Services that replace built-in services or services provided by other packages, are called service overrides.  
  
-   Services, or service overrides, are loaded on demand, that is, the service provider is loaded when the service it provides is requested by another VSPackage.  
  
-   To support on-demand loading, a service provider registers its global services with [!INCLUDE[vsprvs](../codequality/includes/vsprvs_md.md)]. For more information, see [Registering Services](../misc/registering-services.md).  
  
-   After you obtain a service, use [QueryInterface](../Topic/QueryInterface.md) (unmanaged code) or casting (managed code) to get the desired interface, for example:  
  
    ```vb#  
    TryCast(GetService(GetType(SVsActivityLog)), IVsActivityLog)  
    ```  
  
    ```c#  
    GetService(typeof(SVsActivityLog)) as IVsActivityLog;  
  
    ```  
  
-   Managed code refers to a service by its type, whereas unmanaged code refers to a service by its GUID.  
  
-   When [!INCLUDE[vsprvs](../codequality/includes/vsprvs_md.md)] loads a VSPackage, it passes a service provider to the VSPackage to give the VSPackage access to global services. This is referred to as "siting" the VSPackage.  
  
-   VSPackages can be service providers for the objects they create. For example, a form might send a request for a color service to its frame, which might pass the request to [!INCLUDE[vsprvs](../codequality/includes/vsprvs_md.md)].  
  
-   Managed objects that are deeply nested, or not sited at all, may call \<xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService*> for direct access to global services. For more information, see [How to: Use GetGlobalService](../misc/how-to--use-getglobalservice.md).  
  
## See Also  
 [List of Available Services](../extensibility/list-of-available-services.md)   
 [Using and Providing Services](../extensibility/using-and-providing-services.md)   
 [Casting and Type Conversions](../Topic/Casting%20and%20Type%20Conversions%20\(C%23%20Programming%20Guide\).md)   
 [Casting](../Topic/Casting.md)