---
title: "Compiler Error CS1510"
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
ms.assetid: 3f5a69f1-7672-4194-a4ee-5753370fc736
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
# Compiler Error CS1510
A ref or out argument must be an assignable variable  
  
 Only a variable can be passed as a [ref](../Topic/ref%20\(C%23%20Reference\).md) parameter in a method call. A `ref` value is like passing a pointer.  
  
## Example  
 The following sample generates CS1510:  
  
```  
// CS1510.cs  
public class C  
{  
   public static int j = 0;  
  
   public static void M(ref int j)  
   {  
      j++;  
   }  
  
   public static void Main ()  
   {  
      M (ref 2);   // CS1510, can't pass a number as a ref parameter  
      // try the following to resolve the error  
      // M (ref j);  
   }  
}  
```