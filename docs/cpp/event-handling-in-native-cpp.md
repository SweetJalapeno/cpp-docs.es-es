---
title: Control de eventos en C++ nativo | Documentos de Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- event handling [C++], Visual C++
ms.assetid: e4b9219a-15d8-42fb-83c8-6d2e4e087c8d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7b233c8329119753e5753e19fd641c6bea5d8e42
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="event-handling-in-native-c"></a>Control de eventos en C++ nativo

En el control de eventos de C++ nativo, configurar un receptor de origen y de evento de eventos mediante el [event_source](../windows/event-source.md) y [event_receiver](../windows/event-receiver.md) atributos, respectivamente, especificando `type` = `native`. Estos atributos permiten que las clases a las que se aplican desencadenen controlen eventos en un contexto nativo, no COM.

## <a name="declaring-events"></a>Declarar eventos

En una clase de origen de eventos, use la [__event](../cpp/event.md) palabra clave en una declaración de método para declarar el método como un evento. Asegúrese de declarar el método pero no lo defina; si lo hace generará un error del compilador, porque el compilador define el método de manera implícita cuando se convierte en un evento. Los eventos nativos pueden ser métodos con cero o más parámetros. El tipo de valor devuelto puede ser void o cualquier tipo entero.  
  
## <a name="defining-event-handlers"></a>Definir controladores de eventos

En una clase de receptor de eventos, se definen los controladores de eventos, que son métodos con firmas (tipos de valor devuelto, convenciones de llamada y argumentos) que coinciden con el evento que van a controlar.  
  
## <a name="hooking-event-handlers-to-events"></a>Enlazar controladores de eventos a eventos  

También en una clase de receptor de eventos, use la función intrínseca [__hook](../cpp/hook.md) para asociar eventos a controladores de eventos y [__unhook](../cpp/unhook.md) para desasociar eventos de los controladores de eventos. Puede enlazar varios eventos a un controlador de eventos o varios controladores de eventos a un evento.  
  
## <a name="firing-events"></a>Desencadenar eventos  

Para desencadenar un evento, llame simplemente al método declarado como un evento en la clase del origen de eventos. Si se han enlazado controladores al evento, se llamará a los controladores.  
  
### <a name="native-c-event-code"></a>Código de evento de C++ nativo  

En el ejemplo siguiente se muestra cómo activar un evento en C++ nativo. Para compilar y ejecutar el ejemplo, consulte los comentarios del código.  
  
## <a name="example"></a>Ejemplo  
  
### <a name="code"></a>Código  
  
```cpp  
// evh_native.cpp  
#include <stdio.h>  
  
[event_source(native)]  
class CSource {  
public:  
   __event void MyEvent(int nValue);  
};  
  
[event_receiver(native)]  
class CReceiver {  
public:  
   void MyHandler1(int nValue) {  
      printf_s("MyHandler1 was called with value %d.\n", nValue);  
   }  
  
   void MyHandler2(int nValue) {  
      printf_s("MyHandler2 was called with value %d.\n", nValue);  
   }  
  
   void hookEvent(CSource* pSource) {  
      __hook(&CSource::MyEvent, pSource, &CReceiver::MyHandler1);  
      __hook(&CSource::MyEvent, pSource, &CReceiver::MyHandler2);  
   }  
  
   void unhookEvent(CSource* pSource) {  
      __unhook(&CSource::MyEvent, pSource, &CReceiver::MyHandler1);  
      __unhook(&CSource::MyEvent, pSource, &CReceiver::MyHandler2);  
   }  
};  
  
int main() {  
   CSource source;  
   CReceiver receiver;  
  
   receiver.hookEvent(&source);  
   __raise source.MyEvent(123);  
   receiver.unhookEvent(&source);  
}  
```  
  
### <a name="output"></a>Salida  
  
```Output
MyHandler2 was called with value 123.  
MyHandler1 was called with value 123.  
```  
  
## <a name="see-also"></a>Vea también

[Control de eventos](../cpp/event-handling.md)  

