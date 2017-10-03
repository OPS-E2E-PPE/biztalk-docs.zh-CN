---
title: "如何映射到 Web 服务的业务流程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, Web services
- BizTalk Web Services Publishing Wizard, naming conventions
- Web services, orchestrations
- orchestrations, naming conventions
- Web services, naming conventions
ms.assetid: e6a58978-c81c-49f3-9428-9bff60f1ded7
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f101a9a9ab6c0d99e9895433401de08b1380d1e3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-map-orchestrations-to-web-services"></a>如何映射到 Web 服务的业务流程
业务流程可以有多个接收端口。 使用 BizTalk Web 服务发布向导，你选择接收端口作为 Web 服务进行发布。 该向导将为每个接收端口创建一个 Web Services（.asmx 文件）。 如果它们具有相同的接收端口类型，该向导还可以创建一个 Web 服务接收端口的所有 (单向或请求/响应)。 操作变得函数调用。 接收端口中的每个操作将成为一个 Web 方法。 请求操作变得输入的参数。 响应操作变得返回类型。  
  
 如果请求和响应操作相同的 Web 消息类型，输入的参数将成为**ref**和返回类型是**void**。 ASP.NET Web 客户端可以通过合并相同类型的 in 参数和 out 参数更改 Web 方法签名。 例如，ASP.NET Web 客户端可能会更改从某一 BizTalk Web 方法**字符串 myService （字符串一部分）**到**void myService （ref 字符串一部分）**。  
  
 这些操作消息类型定义 Web 方法的签名。 每个消息类型部分是 Web 方法中的一个参数。  
  
## <a name="message-type-part-names-and-target-namespaces"></a>消息类型部分的名称和目标命名空间  
 文档的架构和用户定义的类，同时**XmlRootAttribute**指定是消息类型部分，用于定义目标命名空间。 EDI 架构，而无需用户定义的类**XmlRootAttribute**指定，和内置类型，如**System.String**是不包含定义的目标命名空间的消息类型部分。  
  
|如果消息类型部件名称具有|使用的参数名称|  
|-----------------------------------------|-------------------------|  
|定义的目标命名空间|根元素名称|  
|没有定义的目标命名空间|消息类型部分组成的名称|  
  
> [!NOTE]
>  当多部分消息类型用于响应消息时，BizTalk Web 服务发布向导使用为返回值的第一个消息部分和剩余的消息部分作为输出参数的使用。  
  
## <a name="orchestrations-with-multiple-operations"></a>使用多个操作的业务流程  
 如果您的业务流程包含多个操作，则应设计你的业务流程，有一个接收端口而不是多个接收端口。 此设计阻止 BizTalk Web 服务发布向导创建多个 Web 服务 (.asmx) 文件，并且当所有操作都具有相同的调用模式时才有效-所有单向操作或所有请求-响应操作。 单个接收端口不能包含单向和请求/响应操作。  
  
> [!NOTE]
>  BizTalk Web 服务发布向导显示公共接收端口。 公用接收端口是使用公共类型修饰符的端口类型。 你可以作为 Web 服务发布仅公共端口。 默认端口类型是“内部”。  
  
> [!NOTE]
>  如果你收到定义端口，则为单向，Web 方法的响应类型是**void**和 Web 客户端返回任何信息。 由 SOAP 适配器或业务流程引发的异常不会返回到 Web 客户端。  
  
## <a name="web-services-naming-conventions-for-published-orchestrations"></a>已发布业务流程的 Web Services 命名约定  
 BizTalk Web 服务发布向导生成基于业务流程的命名空间，然后是下划线 (_) 的类型名称，然后是下划线后跟 Web 服务 (.asmx) 文件名称 (\_)，并且接收的名称后跟端口。 下划线 (\_) 替换任何包含句点的部分。 Web 服务的名称始终具有端口名称后追加。  
  
 下表显示如何 BizTalk Web 服务发布向导生成 Web 服务名称。  
  
|与 Web 端口的业务流程|生成的 Web 服务名称|  
|-------------------------------------------|--------------------------------|  
|与一个 Web 端口的一个业务流程|orchestration1_port1.asmx|  
|一个包含两个 Web 端口的业务流程|orchestration1_port1.asmx 和 orchestration1_port2.asmx|  
|两个业务流程与一个 Web 端口每|orchestration1_port1.asmx 和 orchestration2_port2.asmx|  
  
## <a name="see-also"></a>另请参阅  
 [发布作为 Web 服务业务流程](../core/publishing-an-orchestration-as-a-web-service.md)   
 [如何使用发布向导的 BizTalk Web 服务发布作为 Web 服务业务流程](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)