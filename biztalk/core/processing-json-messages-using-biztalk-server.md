---
title: 处理 JSON 消息使用 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6db1421-9478-477c-8645-09eefba06246
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db57847964c7e3da452675945b7d4557ae7cbc85
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986342"
---
# <a name="processing-json-messages-using-biztalk-server"></a>使用 BizTalk Server 处理 JSON 消息
> [!NOTE]
>  本教程仅适用于 BizTalk Server。  
  
 本教程说明了如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 来处理 JSON 消息。 本教程使用自定义管道组件，与 BizTalk Server 现已推出。 这些管道组件可在将 JSON 消息接收到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程中时将消息转换为 XML，并会在向外发送消息时将消息从 XML 转换为 JSON。  
  
## <a name="what-does-this-tutorial-do"></a>本教程有什么作用？  
 为了说明 JSON 处理，我们将创建一个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，它将按给定顺序执行以下操作：  
  
1. 接收 JSON 采购订单，并在接收管道中使用 JSON 解码器组件将 JSON 消息转换为 XML 消息。  
  
2. 使用映射将 XML 采购订单转换为 XML 发票。  
  
3. 在发送管道中，使用 JSON 编码器将 XML 发票转换为 JSON 发票并发送出去。  
  
   ![处理 BizTalk Server 中的 JSON 消息](../core/media/btsjson-flow.png "BTSJSON_Flow")  
  
## <a name="how-to-use-this-tutorial"></a>如何使用本教程？  
 本教程围绕一个示例 (**BTSJSON**)，可以从下载[MSDN 代码库](http://go.microsoft.com/fwlink/?LinkId=403197)。 你可以借助此示例和本教程来了解此示例的构建方式。 你也可以使用本教程来从头创建自己的解决方案。 本教程针对的是第二种方法，以便于你了解此解决方案的构建方式。 另外，本教程尽量与示例保持一致，并对项目（如架构、转换）使用与示例中相同的名称。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [为 JSON 消息生成 XSD 架构](../core/generate-an-xsd-schema-for-json-message.md)  
  
-   [创建处理 JSON 消息的自定义管道](../core/create-custom-pipelines-to-process-json-messages.md)  
  
-   [创建 BizTalk Server 业务流程](../core/create-a-biztalk-server-orchestration.md)  
  
-   [部署并测试应用程序](../core/deploy-and-test-the-application.md)  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 教程](../core/biztalk-server-tutorials.md)