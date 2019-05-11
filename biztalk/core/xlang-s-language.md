---
title: Xlang-s 语言 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, properties
ms.assetid: 97b62f17-5a8d-4d87-8563-1f6d941f027f
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b04a28390546e4e22e5f293d772f88371f76696
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394730"
---
# <a name="xlang-s-language"></a>Xlang-s 语言
XLANG/s 设计为使用 Internet 标准，如 XML、 XSD 和 Web 服务描述语言 (WSDL)，并具有嵌入对处理支持。基于网络的对象和消息。 XLANG/s 可被视为的表达式功能的某些消息传递语言C#。 但是，代码不是 XLANG/s 之间可移植和C#。  
  
 XLANG/s 鼓励明显不同进程和实现。 例如，XLANG/s，以指定的业务流程或协议，并且在其他.NET 等编程语言中实现应用程序，如数据库访问权限的本地方面C#或 Visual Basic.NET。  
  
 XLANG/s 分配和表达式语法以它为模型C#，并应引用C#的确切语法规范。 XLANG/s 定义一组丰富的用于定义业务流程的高级构造。 XLANG/s 为低级别的数据类型，如字符串和整数提供支持，但还定义高级数据类型： 消息、 端口、 相关性和服务的链接。 这些数据类型用于严格地定义与业务流程相关的语义和补充过程控制语句，例如**虽然**或**作用域**。  
  
 XLANG/s 语句通常分为两个类别之一： 简单语句，对其自身，例如**接收**或**发送**，并包含或组是简单的语句的复杂语句或其他复杂语句，如**作用域**，**并行**，并**侦听**。 XLANG/s 中体现的语义是反射的业务流程执行语言由 Microsoft、 IBM 和 BEA 发布定义的业务过程语义的 Web 服务 (BPEL4WS) 规范中定义的那些。  
  
 了解 XLANG/s 的主要构造是可选的因为它们在 BizTalk 业务流程设计器中绘制业务流程关系图生成。 业务流程设计器是用于以可视方式设计业务流程的丰富图形工具。 它将生成具有.odx 扩展名，并且包含在其标头中的其他可视化信息和在其主体的自定义特性信息的 XLANG/s 文件。  
  
> [!NOTE]
>  XLANG/s 语言是专有，并不完全记录。 本部分中显示的语言，可能需要注意的开发您的业务流程的某些部分。 不支持的.odx 文件直接修改。  
  
## <a name="xlangs-programs"></a>XLANG/s 程序  
 最简单的 XLANG/s 程序需要定义消息类型，它可使业务流程启动要使用的某些数据。 业务流程通过端口接收的消息，然后终止。 以下代码是一个示例：  
  
```  
module HelloWorldApp  
{  
     private porttype ptPOReceive  
     {  
      oneway opPOReceive  
      {  
       HelloWorldApp.PurchaseOrder  
      }  
     }  
     private porttype ptPOSend  
     {  
      oneway opPOSend  
      {  
       HelloWorldApp.PurchaseOrder  
      }  
     }  
     private service  HelloWorld  
     {  
      port implements HelloWorldApp.ptPOReceive poPOReceive;  
      port uses HelloWorldApp.ptPOSend poPOSend;  
      message HelloWorldApp.PurchaseOrder msgPO;  
      body ()  
      {  
       activate receive (poPOReceive.opPOReceive, msgPO);  
       send (poPOSend.opPOSend, msgPO);  
       }  
     }  
}  
```  
  
 在前面的 XLANG/s 程序中，`module`关键字定义 XLANG/s 程序的编译期间的单位。 在程序中使用的所有类型，如**porttype**， **correlationsettype**， **servicelinktype**，并**messagetype**— 的作用域在此级别。  
  
 端口是一种构造，XLANG/s 可发送或接收消息的并且端口具有已定义的类型称为**porttype**。 **Porttype**构造定义可用的端口的操作的集合。 这些操作通过端口定义的单个有效的消息交换。 在定义**porttype**， **messagetype**， **servicelinktype**，或者**correlationsettype**构造，XLANG/s 的作者程序实质上创建复杂数据类型定义。 这些定义拥有相同的好处，如在其他语言中的复杂数据类型执行操作：这些抽象概念体现在更高层次的数据类型，它们用于方便的数据类型重复使用。  
  
 **PtPOReceive**端口中前面 HelloWorldApp 模块定义使用一个单向接收端口操作**opPOReceive**。 服务 HelloWorld 块定义此过程，它可能会使用，包括端口和消息变量的任何变量的实际实现。 在此块中的代码的前三行定义端口变量**poPOReceive**并**poPOSend**和消息**msgPO**分别。 正文包含描述该服务并执行行为的参数的代码。 所有变量，除非使用嵌套的作用域块，定义到此级别中的作用都域。 Receive 语句，这是激活接收，接收**msgPO**从消息**poPOReceive.opPOReceive**端口，并创建业务流程的新实例。 接收消息后，send 语句将定向到发送端口的消息。 在前面的代码中，在两个端口声明中**poPOReceive**使用 implements 修饰符，而**poPOSend**使用 uses 修饰符。 Implements 修饰符指示运行时，它将通过该端口接收消息。 使用修饰符指示运行时，它将发送一条消息通过该端口。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [XLANG-s 数据类型](../core/xlang-s-data-types.md)  
  
-   [XLANG-s 语句](../core/xlang-s-statements.md)  
  
-   [XLANG-s 变量和运算符](../core/xlang-s-variables-and-operators.md)  
  
-   [XLANG-s 表达式](../core/xlang-s-expressions.md)  
  
-   [XLANG-s 保留字](../core/xlang-s-reserved-words.md)  
  
-   [XLANG-s 到 BPEL4WS 的类型转换](../core/xlang-s-to-bpel4ws-type-conversions.md)  
  
## <a name="see-also"></a>请参阅  
 [关于 BizTalk 业务流程引擎](../core/about-the-biztalk-orchestration-engine.md)