---
title: Registrador de ATL y los árboles de análisis | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parse trees
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bb5b132e5e55ab5336254acaf4d2d3ae25440697
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="understanding-parse-trees"></a>Entender los árboles de análisis
Puede definir uno o varios árboles de análisis en el script de registrador, donde cada árbol de análisis tiene la forma siguiente:  
  
```  
<root key>{<registry expression>}+  
```  
  
 donde:  
  
```  
<root key> ::= HKEY_CLASSES_ROOT | HKEY_CURRENT_USER |  
    HKEY_LOCAL_MACHINE | HKEY_USERS |  
    HKEY_PERFORMANCE_DATA | HKEY_DYN_DATA |  
    HKEY_CURRENT_CONFIG | HKCR | HKCU |  
    HKLM | HKU | HKPD | HKDD | HKCC  
<registry expression> ::= <Add Key> | <Delete Key>  
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>  
 [<Key Value>][{<Add Key>}]  
<Delete Key> ::= Delete<Key Name>  
<Key Name> ::= '<AlphaNumeric>+'  
<AlphaNumeric> ::= any character not NULL, i.e. ASCII 0  
<Key Value> ::== <Key Type><Key Name>  
<Key Type> ::= s | d  
<Key Value> ::= '<AlphaNumeric>'  
```  
  
> [!NOTE]
> `HKEY_CLASSES_ROOT` y `HKCR` son equivalentes; `HKEY_CURRENT_USER` y `HKCU` son equivalentes; y así sucesivamente.  
  
 Un árbol de análisis puede agregar varias claves y subclaves para la \<clave raíz >. De esta forma, mantiene abierto un identificador de subclave hasta que el analizador ha terminado de analizar todas sus subclaves. Este enfoque es más eficaz que funciona en una sola clave a la vez, tal como se muestra en el ejemplo siguiente:  
  
```  
HKEY_CLASSES_ROOT  
{  
 'MyVeryOwnKey'  
 {  
 'HasASubKey'  
 {  
 'PrettyCool'  
 }  
 }  
}  
```  
  
 En este caso, el registrador abre inicialmente (crea) `HKEY_CLASSES_ROOT\MyVeryOwnKey`. A continuación, ve que `MyVeryOwnKey` tiene una subclave. En lugar de cerrar la clave para `MyVeryOwnKey`, el registrador conserva el identificador y abre (crea) `HasASubKey` utilizando este identificador primario. (El registro del sistema puede ser más lento cuando no hay ningún identificador primario está abierto). Por lo tanto, abrir `HKEY_CLASSES_ROOT\MyVeryOwnKey` y, a continuación, abrir `HasASubKey` con `MyVeryOwnKey` como el elemento primario es más rápido que la apertura `MyVeryOwnKey`, cierre `MyVeryOwnKey`y, a continuación, abrir `MyVeryOwnKey\HasASubKey`.  
  
## <a name="see-also"></a>Vea también  
 [Crear scripts del registrador](../atl/creating-registrar-scripts.md)

