---
title: "Type character cannot be used in a &#39;Sub&#39; declaration because a &#39;Sub&#39; doesn&#39;t return a value"
ms.custom: na
ms.date: 10/01/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: f5a744f0-d312-4fe3-90cd-3cf372a93664
caps.latest.revision: 8
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
# Type character cannot be used in a &#39;Sub&#39; declaration because a &#39;Sub&#39; doesn&#39;t return a value
A `Sub` procedure, like a `Function` procedure, is a separate procedure that can take arguments and perform a series of statements. Unlike a `Function` procedure, a `Sub` does not return a value, and therefore cannot contain a type declaration.  
  
 **Error ID:** BC30303  
  
### To correct this error  
  
-   Change the `Sub` procedure to a `Function` procedure.  
  
## See Also  
 [Sub Procedures](../Topic/Sub%20Procedures%20\(Visual%20Basic\).md)   
 [Function Procedures](../Topic/Function%20Procedures%20\(Visual%20Basic\).md)