---
title: 如何将业务流程映射到 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, Web services
- BizTalk Web Services Publishing Wizard, naming conventions
- Web services, orchestrations
- orchestrations, naming conventions
- Web services, naming conventions
ms.assetid: e6a58978-c81c-49f3-9428-9bff60f1ded7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96fafc1179644b3299b674fe1b863a8ee8f9477d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336291"
---
# <a name="how-to-map-orchestrations-to-web-services"></a>如何将业务流程映射到 Web 服务
业务流程可以有多个接收端口。 使用 BizTalk Web Services 发布向导，选择接收端口，以发布为 Web 服务。 为每个接收端口，该向导将创建一个 Web 服务 （.asmx 文件）。 如果它们是相同的接收端口类型，该向导还可以创建一个 Web 服务进行的所有接收端口 (单向或请求/响应)。 操作变得函数调用。 接收端口中的每个操作将成为 Web 方法。 请求操作变得输入的参数。 响应操作变得返回类型。  
  
 如果请求和响应操作相同的 Web 消息类型，输入的参数将成为**ref**且返回类型为**void**。 ASP.NET Web 客户端可能更改的组合 in 和 out 参数相同类型的 Web 方法签名。 例如，ASP.NET Web 客户端可能会更改 BizTalk Web 方法从**myService （字符串一部分） 的字符串**到**void myService （ref 字符串一部分）**。  
  
 操作消息类型定义 Web 方法的签名。 每个消息类型部分是 Web 方法中的参数。  
  
## <a name="message-type-part-names-and-target-namespaces"></a>消息类型部分组成的名称和目标命名空间  
 文档架构和用户定义类**XmlRootAttribute**指定是消息类型部分，用于定义目标命名空间。 EDI 架构，而无需用户定义的类**XmlRootAttribute**指定，和内置类型，如**System.String**是消息类型部分，而无需定义的目标命名空间。  
  
|如果消息类型部分名称|使用参数名称|  
|-----------------------------------------|-------------------------|  
|定义的目标命名空间|根元素名称|  
|没有定义的目标命名空间|消息类型部分名称|  
  
> [!NOTE]
>  当多部分消息类型用于响应消息时，BizTalk Web Services 发布向导的返回值使用第一个消息部分和剩余的消息部分使用为输出参数。  
  
## <a name="orchestrations-with-multiple-operations"></a>使用多个操作的业务流程  
 如果您的业务流程具有多个操作，则应设计您的业务流程有一个接收端口而不是多个接收端口。 此设计可阻止 BizTalk Web Services 发布向导创建多个 Web 服务 (.asmx) 文件，并仅适用于所有操作都具有相同的调用模式时，所有单向操作或请求-响应的所有操作。 一个接收端口不能包含单向和请求/响应操作。  
  
> [!NOTE]
>  BizTalk Web Services 发布向导显示公共接收端口。 公共接收端口是具有公用类型修饰符的端口类型。 可以将只有公有端口发布为 Web 服务。 默认端口类型为内部。  
  
> [!NOTE]
>  如果在接收端口已定义为单向，则 Web 方法响应类型为**void**和到 Web 客户端返回任何信息。 由 SOAP 适配器或业务流程引发的异常不会返回到 Web 客户端。  
  
## <a name="web-services-naming-conventions-for-published-orchestrations"></a>Web services 已发布的业务流程的命名的约定  
 BizTalk Web Services 发布向导生成 Web 服务 (.asmx) 文件名称基于业务流程命名空间，然后是下划线 (*) 后, 跟类型名称，然后是下划线 (\\*)，并后跟的接收端口的名称。 下划线 (\_) 替换任何包含句点的部分。 Web 服务的名称始终具有附加的端口名称。  
  
 下表显示了如何为 BizTalk Web Services 发布向导生成 Web 服务名称。  
  
|使用 Web 端口的业务流程|生成的 Web 服务名称|  
|-------------------------------------------|--------------------------------|  
|只有一个 Web 端口的一个业务流程|orchestration1_port1.asmx|  
|具有两个 Web 端口的一个业务流程|orchestration1_port1.asmx 和 orchestration1_port2.asmx|  
|两个业务流程使用一个 Web 端口每个|orchestration1_port1.asmx 和 orchestration2_port2.asmx|  
  
## <a name="see-also"></a>请参阅  
 [业务流程发布为 Web 服务](../core/publishing-an-orchestration-as-a-web-service.md)   
 [如何使用 BizTalk Web Services 发布向导业务流程发布为 Web 服务](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)