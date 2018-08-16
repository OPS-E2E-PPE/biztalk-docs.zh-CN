---
title: '教程 3: AS2 教程 |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 018829a9-e670-4b87-bac5-7f7b1332d90e
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b629d1390b6471fb85a0b9e6fb6b605bedb043a6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013462"
---
# <a name="tutorial-3-as2-tutorial"></a>教程 3: AS2 教程
在本教程中，你将设置一个通过 HTTP 传输接收和发送 EDIINT/AS2 编码消息的解决方案。  
  
 **教程解决方案的工作原理**  
  
 该解决方案将执行以下操作：  
  
- 从合作伙伴接收 AS2 消息 (Fabrikam)  
  
- 向合作伙伴异步返回一个 MDN 响应。  
  
- 处理 AS2 消息的 EDI 负载  
  
- 通过 AS2 向合作伙伴 (Fabrikam) 返回一个 997 确认。  
  
- 将包含 EDI 消息负载的 XML 文件路由到本组织 (Contoso) 的后端应用程序。  
  
  > [!NOTE]
  >  此解决方案不使用签名或加密来帮助确保 AS2 消息的安全性。  
  
  **教程组件**  
  
  此解决方案将使用以下各项：  
  
- 一个 BTS Http 接收 ISAPI 筛选器以接收来自发送方的 AS2/EDI 消息 **(/Contoso/BTSHTTPReceive.dll**)。  
  
- 一个 ASPX 网页来通过返回一个 997 确认和 MDN 来模拟合作伙伴 (**http://localhost/Fabrikam/Default.aspx**)。  
  
- 将用于部署 864 架构和其他架构的项目文件 (**Schemas.btproj**)。  
  
- 一个单向 HTTP 接收位置以接收 EDI 文件 (**Receive_AS2**)。 此接收位置使用默认的 AS2EdiReceive 管道，该管道包含 AS2 解码器和 EDI 拆装器。  
  
- 一个动态 HTTP 发送端口返回异步 MDN (**Send_Async_MDN**)。 此发送端口使用包含 AS2 编码器的 AS2Send 管道。  
  
- 一个静态单向 FILE 发送端口以将 EDI 负载路由到后端文件夹的 XML 文件中 (**Send_Payload_EdiXml**)。 此发送端口使用 PassThruTransmit 发送管道。  
  
- 一个静态单向 HTTP 发送端口以通过 AS2 向合作伙伴返回一个 997 确认 (**Send_Async_997**)。 此发送端口使用包括 AS2 编码器的 AS2Send 管道，但无需 EDI 组装器。  
  
- 将用于生成应用程序以将 EDI 文件从 Fabrikam 合作伙伴发送到 BizTalk 项目文件 (**Sender.csproj**)。  
  
  **消息流**  
  
  在完成的解决方案中，消息的流动过程如下图所示：  
  
  ![AS2 教程消息流](../core/media/31710c1d-4070-433e-953d-dcbfd0bb07a0.gif "31710c1d-4070-433e-953d-dcbfd0bb07a0")  
  
  教程组件按以下方式处理消息：  
  
1. 您使用**sender.exe 应用程序**将从合作伙伴 Fabrikam 的原始 EDI/AS2 消息发送到 BizTalk Server 计算机。 Sender.exe 将 EDI/AS2 消息发送到 Contoso 虚拟目录。  
  
   > [!NOTE]
   >  此列表中的事件可能不会按所示顺序发生。  
   >   
   >  测试消息是 \Program Files\Microsoft BizTalk Server 20xx\SDK\AS2 Tutorial 中的 X12_00401_864.edi。  
  
2. **Receive_AS2**单向接收位置接收来自 Fabrikam，使用 BTSHTTPReceive.dll ISAPI 扩展从 Contoso 虚拟目录提取文件的 EDI 消息。 接收管道将解码 AS2 消息、拆装 EDI 交换，然后将该消息 XML 放入 MessageBox。  
  
3. 接收管道为 AS2 消息生成一个 MDN，由于 MDN 设置为异步，因此，接收管道将把该 MDN 放入 MessageBox。  
  
4. 接收管道生成一个 997 确认以响应 EDI 交换，然后将该 997 消息放入 MessageBox。  
  
5. **Send_Payload_EdiXml**静态单向发送端口提取 EDI 负载从 MessageBox 中，对 BTS 进行筛选。MessageType 的上下文属性。  
  
6. 有效负载发送端口将包含到后端 Contoso 应用程序，由 EDI 负载的 XML 文件\\_EDIXMLToContoso 文件夹。 此发送端口使用 PassThruTransmit 发送管道。  
  
7. **Send_Async_MDN**动态发送端口提取异步 MDN 从 MessageBox EdiIntAS.IsAS2AsynchronousMdn 上下文属性进行筛选。  
  
8. 将 MDN 发送端口返回 MDN \\_MDNToFabrikam 文件夹。 由于这是一个动态发送端口，将在消息标头中的回执送达选项行中使用的地址 (**http://localhost/Fabrikam/Default.aspx?Destination=_MDNToFabrikam**) 以将消息路由到\\_MDNToFabrikam 文件夹。  
  
9. **Send_Async_997**发送端口提取 997 消息框，从对 BTS 进行筛选。MessageType 的上下文属性。  
  
10. 997 发送端口使用 HTTP 传输发送 997 消息生成的 EdiReceive 接收管道为\\_997ToFabrikam 文件夹。 发送端口将消息发送到 Fabrikam default.aspx 页，使用 URI **http://localhost/Fabrikam/Default.aspx?Destination=_997ToFabrikam**。 Default.aspx 页然后将发送到 997 \\_997ToFabrikam 文件夹。  
  
    开始学习本教程之前，应了解以下内容：  
  
-   BizTalk Server 管道和管道组件  
  
-   HTTP 适配器  
  
-   接收端口和位置  
  
-   发送端口  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1：AS2 教程的准备工作](../core/step-1-prepare-for-the-as2-tutorial.md)  
  
-   [步骤 2：创建和部署示例 X12 架构](../core/step-2-create-and-deploy-the-sample-x12-schema.md)  
  
-   [步骤 3：配置组织的参与方和业务配置文件](../core/step-3-configure-a-party-and-business-profile-for-your-organization2.md)  
  
-   [步骤 4：为贸易合作伙伴配置参与方和业务配置文件](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner2.md)  
  
-   [步骤 5：配置贸易合作伙伴网页](../core/step-5-configure-the-trading-partner-web-pages.md)  
  
-   [步骤 6：配置 EDI-AS2 接收位置](../core/step-6-configure-the-edi-as2-receive-location.md)  
  
-   [步骤 7：配置 MDN 发送端口](../core/step-7-configure-the-mdn-send-port.md)  
  
-   [步骤 8：配置 997 发送端口](../core/step-8-configure-the-997-send-port.md)  
  
-   [步骤 9：配置 EDI 有效负载发送端口](../core/step-9-configure-the-edi-payload-send-port.md)  
  
-   [步骤 10：配置 X12 和 AS2 贸易合作伙伴协议](../core/step-10-configure-the-x12-and-as2-trading-partner-agreement.md)  
  
-   [步骤 11：测试 AS2 解决方案](../core/step-11-test-the-as2-solution.md)  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 教程](../core/biztalk-server-tutorials.md)