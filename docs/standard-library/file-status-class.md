---
title: file_status (Clase) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- filesystem/std::experimental::filesystem::file_status
- filesystem/std::experimental::filesystem::file_status::operator=
- filesystem/std::experimental::filesystem::file_status::type
- filesystem/std::experimental::filesystem::file_status::permissions
dev_langs:
- C++
ms.assetid: 9781840e-ad22-44dd-ad79-0fabaa94bac4
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::experimental::filesystem::file_status
- std::experimental::filesystem::file_status::operator=
- std::experimental::filesystem::file_status::type
- std::experimental::filesystem::file_status::permissions
ms.workload:
- cplusplus
ms.openlocfilehash: be8f85041099d76a4bbb492aa55c5fb73d870589
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
---
# <a name="filestatus-class"></a>file_status (Clase)

Ajusta un [file_type](../standard-library/filesystem-enumerations.md#file_type) y los [perms](../standard-library/filesystem-enumerations.md#perms) del archivo.

## <a name="syntax"></a>Sintaxis

```cpp
class file_status;
```

## <a name="filestatusfilestatus"></a>file_status::file_status

```cpp
explicit file_status(
   file_type ftype = file_type::none,
   perms mask = perms::unknown) noexcept;

file_status(const file_status&) noexcept = default;

file_status(file_status&&) noexcept = default;

~file_status() noexcept = default;
```

## <a name="filestatusoperator"></a>file_status::operator=

```cpp
file_status& operator=(const file_status&) noexcept = default;
file_status& operator=(file_status&&) nexcept = default;
```

Los operadores predeterminados de asignación de miembros se comportan según lo previsto.

## <a name="type"></a>type

```cpp
file_type type() const noexcept
void type(file_type ftype) noexcept
```

Obtiene o establece el elemento file_type.

## <a name="permissions"></a>permissions

```cpp
perms permissions() const noexcept
void permissions(perms mask) noexcept
```

Obtiene o establece los permisos de archivo.

Use el establecedor para definir un archivo como readonly o quitar este atributo.

## <a name="requirements"></a>Requisitos

**Encabezado:** \<filesystem >

**Namespace:** std::experimental::filesystem, std::experimental::filesystem

## <a name="see-also"></a>Vea también

[Referencia de archivos de encabezado](../standard-library/cpp-standard-library-header-files.md)<br/>
[path (Clase)](../standard-library/path-class.md)<br/>
[\<filesystem>](../standard-library/filesystem.md)<br/>
