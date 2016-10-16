---
title: "Compiler Error CS0434"
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
ms.assetid: 8f8871fc-a4bb-4a9e-ba19-999f4943001e
caps.latest.revision: 14
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
# Compiler Error CS0434
The namespace NamespaceName1 in NamespaceName2 conflicts with the type TypeName1 in NamespaceName3  
  
 This error occurs when an imported type and an imported nested namespace have the same fully qualified name. When that name is referenced, the compiler is unable to distinguish between the two. If you can change the imported source code, you can resolve the error by changing the name of either the type or the namespace so that both are unique within the assembly.  
  
 The following code generates error CS0434.  
  
## Example  
 This code creates the first copy of the type with the identical fully qualified name.  
  
```  
// CS0434_1.cs  
// compile with: /t:library  
namespace TypeBindConflicts   
{  
    namespace NsImpAggPubImp   
    {  
        public class X { }  
    }  
}  
```  
  
## Example  
 This code creates the second copy of the type with the identical fully qualified name.  
  
```  
// CS0434_2.cs  
// compile with: /t:library  
namespace TypeBindConflicts {  
    // Conflicts with another import (import2.cs).  
    public class NsImpAggPubImp { }  
    // Try this instead:  
    // public class UniqueClassName { }  
}  
```  
  
## Example  
 This code references the type with the identical fully qualified name.  
  
```  
// CS0434.cs  
// compile with: /r:cs0434_1.dll /r:cs0434_2.dll  
using TypeBindConflicts;  
public class Test   
{  
    public TypeBindConflicts.NsImpAggPubImp.X n2 = null; // CS0434  
}  
```