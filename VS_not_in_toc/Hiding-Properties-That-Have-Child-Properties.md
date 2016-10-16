---
title: "Hiding Properties That Have Child Properties"
ms.custom: na
ms.date: 10/02/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 6003607e-fc19-4bf9-a299-9f6adf8e92eb
caps.latest.revision: 13
manager: douge
translation.priority.ht: 
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - ru-ru
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - cs-cz
  - pl-pl
  - pt-br
  - tr-tr
---
# Hiding Properties That Have Child Properties
You would want to hide properties that have child properties:  
  
-   If you have nested projects where the parent project programmatically controls some aspects of the child project.  
  
-   If you use a control with a specialized designer and you do not want to give developers full access to all the properties of the control.  
  
-   If you have scope ownership of an object and want to limit the view of properties.  
  
### To hide properties that have child properties  
  
1.  Set the `pfDisplay` parameter in <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.DisplayChildProperties?qualifyHint=False> to `FALSE`.  
  
2.  Set the `pfHide` parameter in <xref:Microsoft.VisualStudio.Shell.Interop.IVsPerPropertyBrowsing.HideProperty?qualifyHint=False> to `TRUE`.  
  
## See Also  
 [Properties Display Grid](../Topic/Properties%20Display%20Grid.md)