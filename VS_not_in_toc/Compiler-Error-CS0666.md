---
title: "Compiler Error CS0666"
ms.custom: na
ms.date: 10/01/2016
ms.devlang: 
  - CSharp
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-csharp
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: 44ad4574-b4a2-487b-8d05-0116762231ab
caps.latest.revision: 10
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
# Compiler Error CS0666
'member' : new protected member declared in struct  
  
 A [struct](../Topic/struct%20\(C%23%20Reference\).md) cannot be [abstract](../Topic/abstract%20\(C%23%20Reference\).md) and is always implicitly [sealed](../Topic/sealed%20\(C%23%20Reference\).md). Because structs do not support inheritance, the concept of a [protected](../Topic/protected%20\(C%23%20Reference\).md) member in a struct makes no sense. For more information, see [Inheritance](../Topic/Inheritance%20\(C%23%20Programming%20Guide\).md).  
  
## Example  
 The following sample generates CS0666:  
  
```  
// CS0666.cs  
class M  
{  
    static void Main()  
    {  
    }  
}  
  
struct S  
{  
    protected int x;   // CS0666  
}  
```