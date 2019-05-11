---
title: 构造 Web 消息 |Microsoft Docs
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
ms.openlocfilehash: fa03c7eae853677c22a0c7160075cad8bdb269cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390326"
---
# <a name="constructing-web-messages"></a>构造 Web 消息
构造 Web 消息从 Web 消息类型。 添加 Web 引用时，BizTalk 会自动创建 Web 消息类型，会基于已添加的 Web 服务的 Web 方法。 您将添加 Web 消息到您的业务流程，消息类型设置为 Web 消息类型之一。 创建单独的消息部分基于基元.NET 或架构类型。 可以构造不包含任何消息部分的 Web 消息。  
  
 **Web 消息类型**  
  
 Reference.odx 中定义的 web 消息类型的正常消息类型相同，但不能修改、 重命名或删除它们。 若要删除 Web 消息类型，必须从您的 BizTalk 项目删除 Web 引用。  
  
 BizTalk 项目添加 Web 服务中创建一个请求和一个响应 Web 消息类型，每个 Web 方法。 如果 Web 方法是单向操作，BizTalk 仅创建请求 Web 消息类型。 请求 Web 消息类型包含一个消息部分的 Web 方法的每个输入参数。 响应 Web 消息类型包含用于返回值的一个消息部分和 Web 方法的每个输出参数的一个消息部分。  
  
 根据 Web 方法参数 （输入或输出），BizTalk 从基元.NET 类型或架构类型创建 Web 消息类型。 如果 Web 方法参数是基元.NET 类型，消息部分使用基元.NET 类型。 如果 Web 方法参数是架构类型，BizTalk 架构类型的 BizTalk 项目将作为添加到 Reference.xsd 中的架构。 架构是消息部分的基础。 可以在 Web 引用文件夹中查找 Reference.xsd。  
  
 或者，您可以创建基元和架构.NET 类型通过调用.NET 类。 使用.NET 类创建消息类型的详细信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。  
  
 **Web 消息**  
  
 Web 消息是您在使用 （调用） Web 服务时使用的消息。 您添加到业务流程是相同的 Web 消息添加常规消息，只不过消息类型设置为添加 Web 引用时 BizTalk 创建的 Web 消息类型之一。  
  
 **消息部分**  
  
 创建 Web 消息后，您构造各个消息部分。 如果消息部分使用基元.NET 类型，则使用**消息赋值**形状。 如果消息部分使用架构类型，则使用**转换**形状或**消息赋值**形状。 有关详细信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何添加 Web 消息](../core/how-to-add-web-messages.md)  
  
-   [如何确定 Web 消息部分类型](../core/how-to-determine-a-web-message-part-type.md)  
  
-   [如何构造 Web 消息部分从基元.NET 类型](../core/how-to-construct-a-web-message-part-from-a-primitive-net-type.md)  
  
-   [如何构造 Web 消息部分从架构类型](../core/how-to-construct-a-web-message-part-from-a-schema-type.md)  
  
-   [如何构造没有消息部分的 Web 消息](../core/how-to-construct-a-web-message-with-no-message-parts.md)