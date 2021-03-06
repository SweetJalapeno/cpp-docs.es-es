---
title: C2200 de errores del compilador a C2299 | Documentos de Microsoft
ms.custom: ''
ms.date: 11/17/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2202
- C2209
- C2210
- C2211
- C2214
- C2215
- C2221
- C2225
- C2230
- C2235
- C2237
- C2239
- C2240
- C2257
- C2260
- C2263
- C2265
- C2269
- C2278
- C2281
- C2282
- C2288
- C2291
- C2294
helpviewer_keywords:
- C2202
- C2209
- C2210
- C2211
- C2214
- C2215
- C2221
- C2225
- C2230
- C2235
- C2237
- C2239
- C2240
- C2257
- C2260
- C2263
- C2265
- C2269
- C2278
- C2281
- C2282
- C2288
- C2291
- C2294
dev_langs:
- C++
ms.assetid: 9b36d11b-9510-4390-96f1-0c9235124d14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 567cd6a9cbb042027b13056fe50330b31f326529
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-errors-c2200-through-c2299"></a>C2200 de errores del compilador a C2299

Los artículos de esta sección de la documentación explican un subconjunto de los mensajes de error generados por el compilador.

[!INCLUDE[error-boilerplate](../../error-messages/includes/error-boilerplate.md)]

## <a name="error-messages"></a>Mensajes de error

|Error|Mensaje|
|-----------|-------------|
|[Error del compilador C2200](compiler-error-c2200.md)|'*función*': ya se ha definido (función)|
|[Error del compilador C2201](compiler-error-c2201.md)|'*identificador*': debe tener vinculación externa para exportar e importar|
|C2202 de Error del compilador|'*función*': no todas las rutas de acceso de control devuelven un valor|
|[Error del compilador C2203](compiler-error-c2203.md)|Eliminar operador no puede especificar límites de matriz|
|[Error del compilador C2204](compiler-error-c2204.md)|'*tipo*': se encuentra entre paréntesis de definición de tipo|
|[Error del compilador C2205](compiler-error-c2205.md)|'*identificador*': no se puede inicializar variables extern con ámbito de bloque|
|[Error del compilador C2206](compiler-error-c2206.md)|'*función*': typedef no se puede usar para la definición de función|
|[Error del compilador C2207](compiler-error-c2207.md)|'*miembro*': un miembro de una plantilla de clase no puede adquirir un tipo de función|
|[Error del compilador C2208](compiler-error-c2208.md)|'*tipo*': no hay miembros definidos con este tipo|
|C2209 de Error del compilador|'*identificador*': no se puede usar alias en las declaraciones de constructor|
|C2210 de Error del compilador|'*identificador*': no se puede usar el módulo expansiones como argumentos a parámetros no empaquetados en plantillas de alias|
|C2211 de Error del compilador|Un destructor no virtual en una clase ref que se deriva de una clase ref con un destructor público también debe ser público|
|[Error del compilador C2212](compiler-error-c2212.md)|'*identificador*': __based no está disponible para punteros a funciones|
|[Error del compilador C2213](compiler-error-c2213.md)|'*identificador*': argumento no válido para __based|
|C2214 de Error del compilador|los punteros basados en 'void' requieren el uso de: >|
|C2215 de Error del compilador|'*palabra clave*' no se puede usar con ' / arch: SSE'|
|[Error del compilador C2216](compiler-error-c2216.md)|'*palabraclave1*'no se puede usar con'*palabraclave2*'|
|[Error del compilador C2217](compiler-error-c2217.md)|'*atributo1*'requiere'*atributo2*'|
|[Error del compilador C2218](compiler-error-c2218.md)|'*calltype*' no se puede usar con ' / arch: IA32'|
|[Error del compilador C2219](compiler-error-c2219.md)|error de sintaxis: el calificador de tipo debe ser posterior a ' *'|
|[Error del compilador C2220](compiler-error-c2220.md)|Advertencia tratada como error - no '*filetype*' archivo generado|
|C2221 de Error del compilador|Obsoleto.|
|[Error del compilador C2222](compiler-error-c2222.md)|tipo inesperado '*tipo*': se esperaba una clase base o miembro|
|[Error del compilador C2223](compiler-error-c2223.md)|izquierdo de ' ->*identificador*' debe señalar a struct/union|
|[Error del compilador C2224](compiler-error-c2224.md)|izquierdo de '. *identificador*' debe tener el tipo struct/union|
|C2225 de Error del compilador|Obsoleto.|
|[Error del compilador C2226](compiler-error-c2226.md)|error de sintaxis: tipo inesperado '*tipo*'|
|[Error del compilador C2227](compiler-error-c2227.md)|izquierdo de ' ->*identificador*' debe señalar al tipo de clase/struct/union/generic|
|[Error del compilador C2228](compiler-error-c2228.md)|izquierdo de '. *identificador*' debe tener clase/estructura/unión|
|[Error del compilador C2229](compiler-error-c2229.md)|clase/estructura/unión '*tipo*' tiene una matriz de tamaño cero no válida|
|C2230 de Error del compilador|no se pudo encontrar el módulo '*nombre*'|
|[Error del compilador C2231](compiler-error-c2231.md)|'. *identificador*': el operando izquierdo señala a 'class/struct/union', use '->'|
|[Error del compilador C2232](compiler-error-c2232.md)|' ->*identificador*': operando izquierdo contiene ' class/struct/union ' tipo'.' use|
|[Error del compilador C2233](compiler-error-c2233.md)|'*identificador*': las matrices de objetos que contienen matrices de tamaño cero no son válidas|
|[Error del compilador C2234](compiler-error-c2234.md)|*identificador de*': las matrices de referencias son válidas|
|C2235 de Error del compilador|Obsoleto.|
|[Error del compilador C2236](compiler-error-c2236.md)|token inesperado '*token*'. Compruebe si olvidó un ';'|
|C2237 de Error del compilador|declaración de módulo múltiple|
|[Error del compilador C2238](compiler-error-c2238.md)|tokens inesperados anteriores '*token*'|
|C2239 de Error del compilador|'*función*': si intenta eliminar una función de __declspec (dllexport)|
|C2240 de Error del compilador|Obsoleto.|
|[Error del compilador C2241](compiler-error-c2241.md)|'*identificador*': acceso a miembros está restringido|
|[Error del compilador C2242](compiler-error-c2242.md)|un nombre typedef no puede seguir a class/struct/union|
|[Error del compilador C2243](compiler-error-c2243.md)|'*conversion_type*': conversión de '*type1*'to'*type2*' existe, pero es inaccesible|
|[Error del compilador C2244](compiler-error-c2244.md)|'*identificador*': no se puede hacer coincidir la definición de función con una declaración existente|
|[Error del compilador C2245](compiler-error-c2245.md)|función miembro inexistente '*función*' especificada como friend (la firma de la función miembro no coincide con ninguna sobrecarga)|
|[Error del compilador C2246](compiler-error-c2246.md)|'*identificador*': miembro de datos estático no válido en la clase definida localmente|
|[Error del compilador C2247](compiler-error-c2247.md)|'*identificador*' no es accesible porque '*class1*'utiliza'*especificador*' para heredar de'*clase2*'|
|[Error del compilador C2248](compiler-error-c2248.md)|'*identificador*': no se puede tener acceso a *accesibilidad* *miembro* declarados en clase*clase*'|
|[Error del compilador C2249](compiler-error-c2249.md)|'*identificador*': ninguna ruta de acceso sea accesible a *accesibilidad* *miembro* declarado en la base virtual '*clase*'|
|[Error del compilador C2250](compiler-error-c2250.md)|'*identificador*': herencia ambigua de *clase*::*miembro*'|
|[Error del compilador C2251](compiler-error-c2251.md)|espacio de nombres '*espacio de nombres*'no tiene un miembro'*identificador*'-¿Quiso decir '*miembro*'?|
|[Error del compilador C2252](compiler-error-c2252.md)|creación de instancias explícita de una plantilla solo se puede producir en el ámbito de espacio de nombres|
|[Error del compilador C2253](compiler-error-c2253.md)|'*función*': el especificador puro o invalidación abstracto sólo se permite en la función virtual|
|[Error del compilador C2254](compiler-error-c2254.md)|'*función*': el especificador puro o invalidación abstracto no se permite en la función friend|
|[Error del compilador C2255](compiler-error-c2255.md)|'*elemento*': no se permite fuera de una definición de clase|
|[Error del compilador C2256](compiler-error-c2256.md)|uso no válido de especificador friend en '*función*'|
|C2257 de Error del compilador|'*especificador*': no se permite en el tipo de valor devuelto final|
|[Error del compilador C2258](compiler-error-c2258.md)|sintaxis pura no válida, debe ser '= 0'|
|[Error del compilador C2259](compiler-error-c2259.md)|'*clase*': no se puede crear una instancia de clase abstracta|
|C2260 de Error del compilador|'*especificador*': especificador de ensamblado de confianza InternalsVisibleToAttribute no válido|
|[Error del compilador C2261](compiler-error-c2261.md)|'*cadena*': referencia de ensamblado no es válida y no se puede resolver|
|[Error del compilador C2262](compiler-error-c2262.md)|'*especificador*': las declaraciones InternalsVisibleTo no pueden tener una versión, referencia cultural o arquitectura de procesador especificada|
|C2263 de Error del compilador|Obsoleto.|
|[Error del compilador C2264](compiler-error-c2264.md)|'*función*': error en la declaración o definición de función; la función no llamado a|
|Error del compilador C2265|Obsoleto.|
|[Error del compilador C2266](compiler-error-c2266.md)|'*identificador*': referencia a una matriz delimitada que no sea constante no es válida|
|[Error del compilador C2267](compiler-error-c2267.md)|'*función*': las funciones static con ámbito de bloque no son válidas|
|[Error del compilador C2268](compiler-error-c2268.md)|'*función*' es una auxiliar de biblioteca predefinida para el compilador. Aplicaciones auxiliares de biblioteca no se admiten con/GL; Compile el archivo objeto '*filename*' sin/GL.|
|C2269 de Error del compilador|no se puede crear un puntero o referencia a un tipo de función completo (requiere el puntero a miembro)|
|[Error del compilador C2270](compiler-error-c2270.md)|'*función*': modificadores no permitidos en las funciones no miembro|
|[Error del compilador C2271](compiler-error-c2271.md)|'*función*': new o delete no puede tener modificadores de lista formales|
|[Error del compilador C2272](compiler-error-c2272.md)|'*función*': modificadores no permitidos en funciones miembro estáticas|
|[Error del compilador C2273](compiler-error-c2273.md)|'*tipo*': no es válido como lado derecho del operador '->'|
|[Error del compilador C2274](compiler-error-c2274.md)|'*tipo*': no es válido como lado derecho de '.' operador|
|[Error del compilador C2275](compiler-error-c2275.md)|'*tipo*': uso no válido de este tipo como una expresión.|
|[Error del compilador C2276](compiler-error-c2276.md)|'*operador*': operación no válida en la expresión de función miembro enlazada|
|[Error del compilador C2277](compiler-error-c2277.md)|'*función*': no se puede adquirir la dirección de esta función miembro|
|C2278 de Error del compilador|Obsoleto.|
|[Error del compilador C2279](compiler-error-c2279.md)|especificación de excepción no puede aparecer en una declaración typedef|
|[Error del compilador C2280](compiler-error-c2280.md)|'*clase*::*función*': intentando hacer referencia a una función eliminada|
|C2281 de Error del compilador|'*clase*::*función*': solo se puede eliminar una función en la primera declaración|
|C2282 de Error del compilador|'*function1*'no puede invalidar'*function2*'|
|[Error del compilador C2283](compiler-error-c2283.md)|'*identificador*': el especificador puro o invalidación abstracto no se permite en la clase o estructura sin nombre.|
|C2284 de Error del compilador|'*función*': argumento no válido para la función intrínseca, parámetro *número*|
|[Error del compilador C2285](compiler-error-c2285.md)|punteros a la representación de los miembros ya se ha determinado - se ha omitido pragma|
|[Error del compilador C2286](compiler-error-c2286.md)|punteros a miembros de '*identificador*' representación ya está establecida en *herencia* -se omite la declaración|
|[Error del compilador C2287](compiler-error-c2287.md)|'*identificador*': representación de herencia: '*inheritiance*'es menos general que requerido'*herencia*'|
|C2288 de Error del compilador|Obsoleto.|
|[Error del compilador C2289](compiler-error-c2289.md)|el mismo calificador de tipo se ha utilizado más de una vez|
|[Error del compilador C2290](compiler-error-c2290.md)|Omitidas la sintaxis de C++ 'asm'. Use __asm.|
|C2291 de Error del compilador|No se puede exportar un espacio de nombres anónimo.|
|[Error del compilador C2292](compiler-error-c2292.md)|'*identificador*': representación de herencia de mejor caso: *inheritance1*' declarado pero '*y herencia 2*' necesario|
|[Error del compilador C2293](compiler-error-c2293.md)|'*identificador*': no es válido tener una variable miembro como especificador __based|
|C2294 de Error del compilador|no se puede exportar símbolos '*identificador*' porque tiene vinculación interna|
|[Error del compilador C2295](compiler-error-c2295.md)|carácter de escape '*caracteres*': no es válido en la definición de macro|
|[Error del compilador C2296](compiler-error-c2296.md)|'*operador*': operando no es válido; tiene el tipo '*tipo*'|
|[Error del compilador C2297](compiler-error-c2297.md)|'*operador*': operando no es válido; tiene el tipo '*tipo*'|
|[Error del compilador C2298](compiler-error-c2298.md)|llamada a enlazar el puntero a una función miembro que falta|
|[Error del compilador C2299](compiler-error-c2299.md)|'*función*': cambio de comportamiento: una especialización explícita no puede ser un constructor de copias o el operador de asignación de copia|
