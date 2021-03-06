---
title: SET_PARAM_TYPE | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- SET_PARAM_TYPE
dev_langs:
- C++
helpviewer_keywords:
- SET_PARAM_TYPE macro
ms.assetid: 85979070-2d55-4c67-94b1-9b9058babc59
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9ab4884032425f13c2cc506d6e66c955eb439f7d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="setparamtype"></a>SET_PARAM_TYPE
Especifica las macros de `COLUMN_ENTRY` que siguen la entrada, salida o la entrada y salida de macro de `SET_PARAM_TYPE` .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
SET_PARAM_TYPE(type)  
  
```  
  
#### <a name="parameters"></a>Parámetros  
 `type`  
 [in] El tipo del conjunto para el parámetro.  
  
## <a name="remarks"></a>Comentarios  
 Los proveedores solo admiten los tipos de entrada y salida de parámetros admitidos por el origen de datos subyacente. El tipo es una combinación de uno o más valores **DBPARAMIO** (vea [Estructuras DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) en la *Referencia del programador de OLE DB*):  
  
-   **DBPARAMIO_NOTPARAM** El descriptor de acceso no tiene ningún parámetro. Normalmente, establece **eParamIO** en este valor en los descriptores de acceso de la fila para recordar al usuario que los parámetros se omiten.  
  
-   **DBPARAMIO_INPUT** Un parámetro de entrada.  
  
-   **DBPARAMIO_OUTPUT** Un parámetro de salida.  
  
-   **DBPARAMIO_INPUT &#124; DBPARAMIO_OUTPUT** el parámetro es una entrada y un parámetro de salida.  
  
## <a name="example"></a>Ejemplo  
```
cpp  
class CArtistsProperty
{
public:
   short m_nReturn;
   short m_nAge;
   TCHAR m_szFirstName[21];
   TCHAR m_szLastName[31];

BEGIN_PARAM_MAP(CArtistsProperty)
   SET_PARAM_TYPE(DBPARAMIO_OUTPUT)
   COLUMN_ENTRY(1, m_nReturn)
   SET_PARAM_TYPE(DBPARAMIO_INPUT)
   COLUMN_ENTRY(2, m_nAge)
END_PARAM_MAP()

BEGIN_COLUMN_MAP(CArtistsProperty)
   COLUMN_ENTRY(1, m_szFirstName)
   COLUMN_ENTRY(2, m_szLastName)
END_COLUMN_MAP()

   HRESULT OpenDataSource()
   {
      CDataSource _db;
      _db.Open();
      return m_session.Open(_db);
   }

   void CloseDataSource()
   {
      m_session.Close();
   }

   CSession m_session;

   DEFINE_COMMAND_EX(CArtistsProperty, L" \
      { ? = SELECT Age FROM Artists WHERE Age < ? }")
};
``` 
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** atldbcli.h  
  
## <a name="see-also"></a>Vea también  
 [Macros y funciones globales para las plantillas de consumidor OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)