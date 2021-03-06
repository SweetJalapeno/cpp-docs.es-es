---
title: -SECTION (EDITBIN) | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /section
dev_langs:
- C++
helpviewer_keywords:
- -SECTION editbin option
- SECTION editbin option
- alignment characters in sections
- /SECTION editbin option
ms.assetid: 4680ab4e-c984-4251-8241-93440cad7615
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e29e258b4fb661cfa06e057704bba983ad924f34
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="section-editbin"></a>/SECTION (EDITBIN)
```  
/SECTION:name[=newname][,attributes][alignment]  
```  
  
## <a name="remarks"></a>Comentarios  
 Esta opción cambia los atributos de una sección reemplazando los atributos que se establecieron cuando se compiló o vinculó el archivo objeto de la sección.  
  
 Después de los dos puntos ( **:** ), especifique la *nombre* de la sección. Para cambiar el nombre de sección, siga *nombre* con un signo igual (=) y un *newname* para la sección.  
  
 Para establecer o cambiar la sección `attributes`, especifique una coma (**,**) seguido por uno o varios caracteres de atributos. Para invalidar un atributo, preceden su carácter con un signo de exclamación (!). Los siguientes caracteres especifican atributos de memoria:  
  
|Atributo|Parámetro|  
|---------------|-------------|  
|c|code|  
|d|Descartable|  
|h|ejecutable|  
|i|datos inicializados|  
|k|memoria virtual almacenada en caché|  
|m|Quitar vínculo|  
|o|información de vínculo|  
|p|memoria virtual paginada|  
|r|leer|  
|s|shared|  
|u|datos sin inicializar|  
|s|escribir|  
  
 Para controlar *alineación*, especifique el carácter **A** seguido de uno de los siguientes caracteres para establecer el tamaño de alineación en bytes, como se indica a continuación:  
  
|Carácter|Tamaño de alineación en bytes|  
|---------------|-----------------------------|  
|1|1|  
|2|2|  
|4|4|  
|8|8|  
|p|16|  
|m|32|  
|s|64|  
|x|sin alineación|  
  
 Especifique el `attributes` y *alineación* caracteres como una cadena con ningún espacio en blanco. Los caracteres no distinguen mayúsculas de minúsculas.  
  
## <a name="see-also"></a>Vea también  
 [Opciones de EDITBIN](../../build/reference/editbin-options.md)