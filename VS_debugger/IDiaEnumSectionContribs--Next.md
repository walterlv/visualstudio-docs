---
title: "IDiaEnumSectionContribs::Next"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - vs-ide-debug
ms.tgt_pltfrm: na
ms.topic: article
ms.assetid: a6bb2adb-ee6d-4f3c-ab5b-e89361c8880e
caps.latest.revision: 7
manager: ghogen
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
# IDiaEnumSectionContribs::Next
Retrieves a specified number of section contributions in the enumeration sequence.  
  
## Syntax  
  
```cpp#  
HRESULT Next(   
   ULONG                celt,   
   IDiaSectionContrib** rgelt,  
   ULONG*               pceltFetched  
);  
```  
  
#### Parameters  
 celt  
 [in] The number of section contributions in the enumerator to be retrieved.  
  
 rgelt  
 [out] An array that is to be filled with the [IDiaSectionContrib](../VS_debugger/IDiaSectionContrib.md) objects that represent the desired section contributions.  
  
 pceltFetched  
 [out] Returns the number of section contributions in the enumerator fetched.  
  
## Return Value  
 If successful, returns `S_OK`. Returns `S_FALSE` if there are no more section contributions. Otherwise, returns an error code.  
  
## See Also  
 [IDiaEnumSectionContribs](../VS_debugger/IDiaEnumSectionContribs.md)   
 [IDiaSectionContrib](../VS_debugger/IDiaSectionContrib.md)