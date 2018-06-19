---
title: XLANG-s 语言 |Microsoft 文档
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
ms.openlocfilehash: 2329d4bc42617d70227481a0d70064d368f3c0e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22290909"
---
# <a name="xlang-s-language"></a>XLANG-s 语言
XLANG/s 设计为使用 Internet 标准，如 XML、 XSD 和 Web 服务描述语言 (WSDL)，并具有嵌入支持使用。基于网络的对象和消息。 作为消息传递使用的某些表达式功能的 C# 语言，可以查看 XLANG/s。 但是，代码不可移植 XLANG/s 和 C# 之间。  
  
 XLANG/s 鼓励过程和实现之间形成清晰的隔离。 例如，业务流程或协议指定以 XLANG/秒，并且在其他.NET 编程语言，例如 C# 或 Visual Basic.NET 中实现应用程序，如数据库访问的本地方面。  
  
 之后 C# 中，制定 XLANG/s 分配和表达式语法，并且应引用确切语法的 C# 规范。 XLANG/s 定义一组丰富的用于定义业务流程的高级构造。 虽然 XLANG/s 为低级别的数据类型，如字符串和整数提供支持，还定义了高级的数据类型： 消息、 端口、 相关性和服务的链接。 这些数据类型可用于进行严格定义的业务流程，与关联的语义，过程补充控件语句如**时**或**作用域**。  
  
 XLANG/s 语句通常分为两个类别之一： 如作用于其自己的简单语句**接收**或**发送**，和复杂语句包含或任一简单语句组合或其他复杂的语句，如**作用域**，**并行**，和**侦听**。 包含于 XLANG/s 中的语义是由 Microsoft、 IBM 和 BEA 业务进程语义的定义已发布的 Web 服务 (BPEL4WS) 规范业务流程执行语言中所定义的反射。  
  
 了解 XLANG/s 的主要构造是可选的因为产生结果绘制 BizTalk 业务流程设计器中的业务流程关系图。 业务流程设计器是用于以可视方式设计业务流程的丰富图形工具。 它会生成.odx 扩展并包含其标头中的其他可视化信息和其主体中的自定义特性信息的 XLANG/s 文件。  
  
> [!NOTE]
>  XLANG/s 语言是专用的并且不完全了介绍。 本部分显示的语言，可能需要注意的开发你的业务流程的某些部分。 不支持.odx 文件的直接修改。  
  
## <a name="xlangs-programs"></a>XLANG/s 程序  
 最简单的 XLANG/s 程序需要一种消息类型定义，这将给予一些数据来开始使用业务流程。 业务流程通过端口收到消息，然后终止。 下面的代码是一个示例：  
  
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
  
 在前面的 XLANG/s 程序中，`module`关键字定义的程序 XLANG/s 的编译单元。 在程序中使用的所有类型，如**porttype**， **correlationsettype**， **servicelinktype**，和**messagetype**-在范围此级别。  
  
 端口是一种 XLANG/s 可以发送或接收消息到或从，构造和端口都具有已定义的类型调用**porttype**。 **Porttype**构造定义可在端口的操作的集合。 这些操作通过端口定义是单个的有效消息交换。 在定义**porttype**， **messagetype**， **servicelinktype**，或**correlationsettype**构造，XLANG/s 的作者程序实质上创建复杂数据类型定义。 这些定义具有相同的优势，与复杂数据类型在其他语言： 它们抽象体现在数据类型添加到更高级别概念，它们允许进行以便重复使用的数据类型。  
  
 **PtPOReceive**端口中前面的 HelloWorldApp 模块定义使用单向接收端口操作**opPOReceive**。 服务 HelloWorld 块定义在过程和任何它可能会使用，包括端口和消息的变量的变量的实际实现。 在此块中的代码的前三行定义端口变量**poPOReceive**和**poPOSend**和消息**msgPO**分别。 正文包含描述服务，以及执行行为的参数的代码。 所有变量，除非定义嵌套的范围块，到此级别中的作用都域。 Receive 语句，这是激活接收，接收**msgPO**消息从**poPOReceive.opPOReceive**端口，创建业务流程的新实例。 收到的消息后，发送语句将重定向到发送端口的消息。 在前面的代码中，两个端口声明中**poPOReceive**使用实现修饰符，而**poPOSend**使用使用修饰符。 实现修饰符指示运行时，它将通过该端口接收消息。 使用修饰符指示运行时，它将发送一条消息通过该端口。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [XLANG-s 数据类型](../core/xlang-s-data-types.md)  
  
-   [XLANG-s 语句](../core/xlang-s-statements.md)  
  
-   [XLANG-s 变量和运算符](../core/xlang-s-variables-and-operators.md)  
  
-   [XLANG-s 表达式](../core/xlang-s-expressions.md)  
  
-   [XLANG-s 保留字](../core/xlang-s-reserved-words.md)  
  
-   [XLANG-s 的 BPEL4WS 类型转换](../core/xlang-s-to-bpel4ws-type-conversions.md)  
  
## <a name="see-also"></a>另请参阅  
 [有关 BizTalk 业务流程引擎](../core/about-the-biztalk-orchestration-engine.md)