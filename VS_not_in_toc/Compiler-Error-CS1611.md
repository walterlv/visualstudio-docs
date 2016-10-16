---
title: "Compiler Error CS1611"
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
ms.assetid: 48bfba77-6be2-4242-b1d2-98bf471b6d1e
caps.latest.revision: 7
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
# Compiler Error CS1611
The params parameter cannot be declared as ref or out  
  
 The keywords [ref](../Topic/ref%20\(C%23%20Reference\).md) or [out](../Topic/out%20\(C%23%20Reference\).md) cannot be used with the [params](../Topic/params%20\(C%23%20Reference\).md) keyword.  
  
 The following sample generates CS1611:  
  
```  
// CS1611.cs  
public class MyClass  
{  
   public static void Test(params ref int[] a)   // CS1611, remove ref  
   {  
   }  
  
   public static void Main()  
   {  
      Test(1);  
   }  
}  
```