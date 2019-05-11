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
ms.openlocfilehash: 7336b515d196fadc6e8e6cc4fe0bcf500b883189
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396984"
---
# <a name="processing-json-messages-using-biztalk-server"></a>使用 BizTalk Server 处理 JSON 消息
> [!NOTE]
>  本教程仅适用于 BizTalk Server。  
  
 本教程演示如何处理 JSON 消息使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 本教程使用自定义管道组件，与 BizTalk Server 现已推出。 这些管道组件将 JSON 消息转换为 XML (接收到消息时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]业务流程，并将转换该消息从 XML 到 JSON 时将消息发送。  
  
## <a name="what-does-this-tutorial-do"></a>此教程，请执行是什么？  
 为了说明 JSON 处理，我们将创建[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以下内容，按给定顺序执行的：  
  
1. 接收 JSON 采购订单并在接收管道中，使用 JSON 解码器组件将转换为 XML 消息的 JSON 消息。  
  
2. 将 XML 采购订单转换为使用映射的 XML 发票。  
  
3. 在发送管道中，使用 JSON 编码器将 XML 转换为 JSON 发票发票并发送出去。  
  
   ![处理 BizTalk Server 中的 JSON 消息](../core/media/btsjson-flow.png "BTSJSON_Flow")  
  
## <a name="how-to-use-this-tutorial"></a>如何使用此教程？  
 本教程围绕一个示例 (**BTSJSON**)，可以从下载[MSDN 代码库](http://go.microsoft.com/fwlink/?LinkId=403197)。 可使用该示例并浏览本教程来了解该示例如何生成。 或者，可以使用本教程来创建你自己的解决方案从头。 本教程主要用于第二种方法，以便您了解此解决方案的构建方式。 此外，尽可能多地，教程是与示例一致，作为使用与示例中使用的项目 （例如，架构、 转换） 相同的名称。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [为 JSON 消息生成 XSD 架构](../core/generate-an-xsd-schema-for-json-message.md)  
  
-   [创建处理 JSON 消息的自定义管道](../core/create-custom-pipelines-to-process-json-messages.md)  
  
-   [创建 BizTalk Server 业务流程](../core/create-a-biztalk-server-orchestration.md)  
  
-   [部署并测试应用程序](../core/deploy-and-test-the-application.md)  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 教程](../core/biztalk-server-tutorials.md)