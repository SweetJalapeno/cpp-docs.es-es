---
title: Cambiar el generador de clases predeterminado y el modelo de agregación | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CComClassFactory class, making the default
- aggregation [C++], using ATL
- aggregation [C++], aggregation models
- defaults [C++], aggregation model in ATL
- default class factory
- class factories, changing default
- CComCoClass class, default class factory and aggregation model
- default class factory, ATL
- defaults [C++], class factory
ms.assetid: 6e040e95-0f38-4839-8a8b-c9800dd47e8c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ce64f2162aa0d5cdf5bcf5e16b56b6989fcaf1ee
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="changing-the-default-class-factory-and-aggregation-model"></a>Cambiar el generador de clases predeterminado y el modelo de agregación
ATL usa [CComCoClass](../atl/reference/ccomcoclass-class.md) para definir el modelo de generador y agregación de clase predeterminado para el objeto. `CComCoClass` Especifica las dos macros siguientes:  
  
-   [DECLARE_CLASSFACTORY](reference/aggregation-and-class-factory-macros.md#declare_classfactory) declara el generador de clases como [CComClassFactory](../atl/reference/ccomclassfactory-class.md).  
  
-   [DECLARE_AGGREGATABLE](reference/aggregation-and-class-factory-macros.md#declare_aggregatable) declara que se puede agregar el objeto.  
  
 Puede invalidar cualquiera de estos valores predeterminados especificando otra macro en la definición de clase. Por ejemplo, para usar [CComClassFactory2](../atl/reference/ccomclassfactory2-class.md) en lugar de `CComClassFactory`, especifique el [macro DECLARE_CLASSFACTORY2](reference/aggregation-and-class-factory-macros.md#declare_classfactory2) macro:  
  
 [!code-cpp[NVC_ATL_COM#2](../atl/codesnippet/cpp/changing-the-default-class-factory-and-aggregation-model_1.h)]  
  
 Otras dos macros que definen un generador de clases son [DECLARE_CLASSFACTORY_AUTO_THREAD](reference/aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) y [DECLARE_CLASSFACTORY_SINGLETON](reference/aggregation-and-class-factory-macros.md#declare_classfactory_singleton).  
  
 ATL también usa el `typedef` mecanismo para implementar el comportamiento predeterminado. Por ejemplo, el `DECLARE_AGGREGATABLE` macro utiliza `typedef` para definir un tipo denominado **_CreatorClass**, que, a continuación, se hace referencia a lo largo de ATL. Tenga en cuenta que en una clase derivada, un `typedef` con el mismo nombre que la clase base `typedef` da como resultado ATL mediante la definición e invalidar el comportamiento predeterminado.  
  
## <a name="see-also"></a>Vea también  
 [Aspectos básicos de los objetos ATL COM](../atl/fundamentals-of-atl-com-objects.md)   
 [Macros de agregación y generador de clases](../atl/reference/aggregation-and-class-factory-macros.md)

