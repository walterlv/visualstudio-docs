---
title: "How to: Debug ASP.NET Exceptions | Microsoft Docs"
ms.custom: ""
ms.date: 11/15/2016
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "debugging [Visual Studio], ASP.NET exceptions"
  - "ASP.NET, exceptions"
  - "exceptions, ASP.NET"
ms.assetid: 1810096e-de8c-435e-be3d-f365d0cd0a6a
caps.latest.revision: 26
author: MikeJo5000
ms.author: mikejo
manager: "ghogen"
---
# How to: Debug ASP.NET Exceptions
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Debugging exceptions is an important part of developing a robust [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] application. General information about how to debug exceptions is at [Managing Exceptions with the Debugger](../debugger/managing-exceptions-with-the-debugger.md).  
  
 To debug unhandled [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] exceptions, you must make sure that the debugger stops for them. The [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] runtime has a top-level exception handler. Therefore, the debugger never breaks on unhandled exceptions by default. To break into the debugger when an exception is thrown, you must select **Break when an exception is: Thrown** setting for that specific exception in the **Exceptions** dialog box.  
  
 If you have enabled Just My Code, **Break when an exception is: Thrown** does not cause the debugger to break immediately if an exception is thrown in a .NET Framework method or other system code. Instead, execution continues until the debugger hits non-system code, then it breaks. As a result, you do not have to step through the system code when an exception occurs.  
  
 Just My Code gives you another option that can be even more useful: **Break when an exception is: User-unhandled**. If you choose this setting for an exception, the debugger will break execution in user code, but only if the exception is not caught and handled by the user code. This setting negates the effect of the top-level [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] exception handler, because that handler is in non-user code.  
  
### To enable debugging of ASP.NET exceptions with Just My Code  
  
1.  On the **Debug** menu, click **Exceptions**.  
  
     The **Exceptions** dialog box appears.  
  
2.  On the **Common Language Runtime Exceptions** row, select **Thrown** or **User-unhandled**.  
  
     To use the **User-unhandled** setting, **Just My Code** must be enabled..  
  
### To use best practices for ASP.NET exception handling  
  
-   Place `try … catch` blocks around code that can throw exceptions that you can anticipate and know how to handle. For example, if the application is making calls to an XML Web Service or directly to a SQL Server, that code should be in **try … catch** blocks because there are numerous exceptions that can occur.



