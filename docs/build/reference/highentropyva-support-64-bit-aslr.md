---
title: -HIGHENTROPYVA (compatibilidad con ASLR de 64 bits) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
ms.assetid: fe35f9f7-d28e-4694-9aeb-a79db06168e0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: de2487cbeff97ded6e95a36393fbbcfbd510e6d0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="highentropyva-support-64-bit-aslr"></a>/HIGHENTROPYVA (Compatibilidad con ASLR de 64 bits)
Especifica que la imagen ejecutable es compatible con la selección aleatoria del diseño del espacio de direcciones (ASLR) de 64 bits de alta entropía.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/HIGHENTROPYVA[:NO]  
```  
  
## <a name="remarks"></a>Comentarios  
 De forma predeterminada, /HIGHENTROPYVA está activado para las imágenes ejecutables de 64 bits. No es aplicable a imágenes ejecutables de 32 bits. Para habilitar esta opción, /DYNAMICBASE también debe estar activado.  
  
 /HIGHENTROPYVA modifica el encabezado de un archivo .dll o .exe para indicar si se admite ASLR con direcciones de 64 bits. Cuando esta opción está establecida en un ejecutable y todos los módulos de los que este depende, un sistema operativo compatible con ASLR de 64 bits puede reorganizar los segmentos de la imagen ejecutable en tiempo de carga mediante el uso de direcciones aleatorias en un espacio de direcciones virtuales de 64 bits. Este gran espacio de direcciones dificulta a un atacante la tarea de adivinar la ubicación de un área de memoria específica.  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Para establecer esta opción del vinculador en Visual Studio  
  
1.  Abra el cuadro de diálogo **Páginas de propiedades** del proyecto. Para obtener más información, consulte [trabajar con configuraciones de proyecto](../../ide/working-with-project-properties.md).  
  
2.  Expanda el **propiedades de configuración** nodo.  
  
3.  Expanda el **vinculador** nodo.  
  
4.  Seleccione el **línea de comandos** página de propiedades.  
  
5.  En **opciones adicionales**, escriba `/HIGHENTROPYVA` o `/HIGHENTROPYVA:NO`.  
  
## <a name="see-also"></a>Vea también  
 [Establecer las opciones del vinculador](../../build/reference/setting-linker-options.md)   
 [Opciones del vinculador](../../build/reference/linker-options.md)