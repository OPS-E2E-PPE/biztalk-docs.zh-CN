---
title: 构造 Web 消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web messages, about Web messages
- Web messages, message types
- Web services, Web messages
- Web messages, parts
- Web messages
- messages, Web messages
ms.assetid: ca1792be-5fba-4f5d-a88e-b854f6a8ce33
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c344bbb836a6524ec1fd2656a5ba3f8bc8fad7d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237981"
---
# <a name="constructing-web-messages"></a>构造 Web 消息
可从 Web 消息类型构造 Web 消息。 添加 Web 引用时，BizTalk 会基于已添加的 Web Services 的 Web 方法自动创建 Web 消息类型。 你可以向业务流程添加 Web 消息，并将消息类型设置为 Web 消息类型之一。 你可以基于基元 .NET 或架构类型创建各消息部分。 构造的 Web 消息可以不包含任何消息部分。  
  
 **Web 消息类型**  
  
 Reference.odx 中定义的 Web 消息类型与一般消息类型相同，不同之处在于你不能对 Web 消息类型进行修改，重命名或删除。 若要删除 Web 消息类型，你必须从 BizTalk 项目删除 Web 引用。  
  
 BizTalk 项目为已添加的 Web Services 中的每个 Web 方法创建一个请求和一个响应 Web 消息类型。 如果 Web 方法是单向操作，BizTalk 仅创建请求 Web 消息类型。 请求 Web 消息类型针对 Web 方法的每个输入参数各包含一个消息部分。 响应 Web 消息类型针对返回值包含一个消息部分，并针对 Web 方法的每个输出参数各包含一个消息部分。  
  
 根据 Web 方法参数（输入或输出），BizTalk 从基元 .NET 类型或架构类型创建 Web 消息类型。 如果 Web 方法参数是基元 .NET 类型，消息部分则使用基元 .NET 类型。 如果 Web 方法参数是架构类型，BizTalk 将此架构类型作为 Reference.xsd 中的架构添加到 BizTalk 项目中。 架构是消息部分的基础。 你可以在 Web 引用文件夹中查找 Reference.xsd。  
  
 另外，你还可以通过调用 .NET 类来创建基元和架构 .NET 类型。 通过使用一个.NET 类创建消息类型的详细信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。  
  
 **Web 消息**  
  
 Web 消息是使用（调用）Web Services 时所使用的消息。 你可以以添加常规消息的方式将 Web 消息添加到业务流程，不同之处在于将消息类型设置为添加 Web 引用时 BizTalk 创建的 Web 消息类型之一。  
  
 **消息部分**  
  
 在创建 Web 消息之后，请构造各个消息部分。 如果消息部分使用基元的.NET 类型，则使用**消息分配**形状。 如果消息部分使用的架构类型，则使用**转换**形状或**消息分配**形状。 有关详细信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何添加 Web 消息](../core/how-to-add-web-messages.md)  
  
-   [如何确定 Web 消息部分类型](../core/how-to-determine-a-web-message-part-type.md)  
  
-   [如何构造从基元.NET 类型的 Web 消息部分](../core/how-to-construct-a-web-message-part-from-a-primitive-net-type.md)  
  
-   [如何构造中的架构类型的 Web 消息部件](../core/how-to-construct-a-web-message-part-from-a-schema-type.md)  
  
-   [如何构造具有任何消息部分的 Web 消息](../core/how-to-construct-a-web-message-with-no-message-parts.md)