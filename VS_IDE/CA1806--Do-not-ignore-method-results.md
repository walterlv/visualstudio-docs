---
title: "CA1806: Do not ignore method results"
ms.custom: na
ms.date: 10/03/2016
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - vs-devops-test
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: fd805687-0817-481e-804e-b62cfb3b1076
caps.latest.revision: 27
manager: douge
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
# CA1806: Do not ignore method results
|||  
|-|-|  
|TypeName|DoNotIgnoreMethodResults|  
|CheckId|CA1806|  
|Category|Microsoft.Usage|  
|Breaking Change|Non Breaking|  
  
## Cause  
 There are several possible reasons for this warning:  
  
-   A new object is created but never used.  
  
-   A method that creates and returns a new string is called and the new string is never used.  
  
-   A COM or P/Invoke method that returns a HRESULT or error code that is never used. Rule Description  
  
 Unnecessary object creation and the associated garbage collection of the unused object degrade performance.  
  
 Strings are immutable and methods such as String.ToUpper returns a new instance of a string instead of modifying the instance of the string in the calling method.  
  
 Ignoring HRESULT or error code can lead to unexpected behavior in error conditions or to low-resource conditions.  
  
## How to Fix Violations  
 If method A creates a new instance of B object that is never used, pass the instance as an argument to another method or assign the instance to a variable. If the object creation is unnecessary, remove the it.-or-  
  
 If method A calls method B, but does not use the new string instance that the method B returns. Pass the instance as an argument to another method, assign the instance to a variable. Or remove the call if it is unnecessary.  
  
 -or-  
  
 If method A calls method B, but does not use the HRESULT or error code that the method returns. Use the result in a conditional statement, assign the result to a variable, or pass it as an argument to another method.  
  
## When to Suppress Warnings  
 Do not suppress a warning from this rule unless the act of creating the object serves some purpose.  
  
## Example  
 The following example shows a class that ignores the result of calling String.Trim.  
  
 [!CODE [FxCop.Usage.DoNotIgnoreMethodResults#1](FxCop.Usage.DoNotIgnoreMethodResults#1)]  
  
## Example  
 The following example fixes the previous violation by assigning the result of String.Trim back to the variable it was called on.  
  
 [!CODE [FxCop.Usage.DoNotIgnoreMethodResults2#1](FxCop.Usage.DoNotIgnoreMethodResults2#1)]  
  
## Example  
 The following example shows a method that does not use an object that it creates.  
  
> [!NOTE]
>  This violation cannot be reproduced in Visual Basic.  
  
 [!CODE [FxCop.Usage.DoNotIgnoreMethodResults3#1](../CodeSnippet/VS_Snippets_CodeAnalysis/FxCop.Usage.DoNotIgnoreMethodResults3#1)]  
  
## Example  
 The following example fixes the previous violation by removing the unnecessary creation of an object.  
  
 [!CODE [FxCop.Usage.DoNotIgnoreMethodResults4#1](../CodeSnippet/VS_Snippets_CodeAnalysis/FxCop.Usage.DoNotIgnoreMethodResults4#1)]  
  
## Example  
 The following example shows a method that ignores the error code that the native method GetShortPathName returns.  
  
 [!CODE [FxCop.Usage.DoNotIgnoreMethodResults5#1](../CodeSnippet/VS_Snippets_CodeAnalysis/FxCop.Usage.DoNotIgnoreMethodResults5#1)]  
  
## Example  
 The following example fixes the previous violation by checking the error code and throwing an exception when the call fails.  
  
 [!CODE [FxCop.Usage.DoNotIgnoreMethodResults6#1](../CodeSnippet/VS_Snippets_CodeAnalysis/FxCop.Usage.DoNotIgnoreMethodResults6#1)]