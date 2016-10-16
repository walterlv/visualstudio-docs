---
title: "Compiler Warning (level 1) CS1635"
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
ms.assetid: e1795880-f7ea-4dca-b15b-4ba549d7ed78
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
# Compiler Warning (level 1) CS1635
Cannot restore warning 'warning code' because it was disabled globally  
  
 This warning occurs if you use the **/nowarn** command line option or project setting to disable a warning for the entire compilation unit, but you use `#pragma warning restore` to attempt to restore that warning. To resolve this error, remove the /nowarn command line option or project setting, or remove the `#pragma warning restore` for any warnings you are disabling via the command line or project settings. For more information, see the [#pragma warning](../Topic/%23pragma%20warning%20\(C%23%20Reference\).md) topic.  
  
 The following sample generates CS1635:  
  
```  
// CS1635.cs  
// compile with: /w:1 /nowarn:162  
  
enum MyEnum {one=1,two=2,three=3};  
  
class MyClass  
{  
    public static void Main()  
    {  
#pragma warning disable 162  
  
    if (MyEnum.three == MyEnum.two)  
        System.Console.WriteLine("Duplicate");  
  
#pragma warning restore 162  
    }  
}  
```