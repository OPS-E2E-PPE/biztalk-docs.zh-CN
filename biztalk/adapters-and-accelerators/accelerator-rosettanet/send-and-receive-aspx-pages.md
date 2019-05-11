---
title: 发送和接收 ASPX 页 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BTARN, ASPX pages
- ASPX pages, initiator
- HTTP adapters
- connections, HTTP adapters
- connections, single-action
- ASPX pages, responder
- single-action connections
- RNIFSend.aspx
- connections, asynchronous
- ASPX pages, about ASPX pages
- double-action connections
- connections, synchronous
- connections, double-action
- ASPX pages
- HTTP adapters, connections
- asynchronous connections
- RNIFReceive.aspx
- synchronous connections
ms.assetid: 21e52390-35d8-44b1-a5cd-1cd60cfe6e61
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d93c41a87465a75adc2047889ff6cb80cdf629fa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281967"
---
# <a name="send-and-receive-aspx-pages"></a>发送和接收 ASPX 页
在 Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ASPX 页是之间的直接接口[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]和 Internet。 两个 ASPX 页是接收页 (RNIFReceive.aspx) 和发送页 (RNIFSend.aspx)。 每个 ASPX 页都是相应的扩展[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管道。 该管道需要 ASPX 页来处理 RosettaNet 实现框架 (RNIF) 标头。 管道执行大部分 HTTP 处理;但是，每个 ASPX 页执行 RNIF 头的 HTTP 处理。 页增强功能中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]HTTP 适配器。  
  
 每个 ASPX 页都是 ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web 应用程序没有用户界面。 它们使用 ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web 安全以确保与外部各方的安全连接。 它们提供了可以在其中实现容错、 可伸缩性和高可用性的服务层。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 安装程序将安装一个 RNIFSend.aspx 页和一个 RNIFReceive.aspx 页上的每个部署[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]。 当发起方或响应程序与其交换消息的贸易合作伙伴[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]使用 ASPX 页将消息发送到，或从伙伴 URL 接收消息。 如果发起方和响应方使用[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]，发起方上的两个 ASPX 页交换消息的响应方上的两个 ASPX 页。 有关详细信息，请参阅"发起方和响应方 ASPX 页的交互方式"下面的子节。  
  
## <a name="send-aspx-page"></a>发送 ASPX 页  
 RNIFSend.aspx 页从 BizTalk HTTP 适配器接收消息。 它创建和将 RNIF 头添加到消息，然后通过 Internet 向合作伙伴发送消息。 HTTP 适配器使用以下命令调用 RNIFSend.aspx:  
  
```  
http://localhost:<port number>/RNIFSend.aspx?<query string>  
```  
  
 查询字符串包括发送页需要将消息发送到合作伙伴，以下数据和必须为合作伙伴来处理该消息的数据：  
  
- 贸易合作伙伴 URL: http://www.\<*地址*\>.com/RNIFReceive.aspx  
  
- 响应类型： sync 或 async  
  
- RNIF 版本：1.1 或 2.0。  
  
  BizTalk HTTP 适配器发送生成的 MIME 消息[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]发起方的 RNIFSend.aspx 页的发送管道。 RNIFSend.aspx 处理该消息，如下所示：  
  
1.  发送页对消息执行验证。  
  
2.  发送页创建基于内容类型、 长度、 ID 和 MIME 版本的多用途 Internet 邮件扩展 (MIME) 标头。 它将 MIME 头和上限和下限 MIME 边界添加到消息中。  
  
3.  对于 RNIF 2.01，发送页，如下所示设置 HTTP 标头的属性：  
  
    1.  它将 X RN 版本属性设置为流程配置设置的版本属性中输入的版本。  
  
    2.  它将 X RN ResponseType 属性设置为 sync 或 async，取决于在流程配置设置中 IsSynchronous 属性的设置。  
  
    3.  它将 Content-length 属性设置为完整消息的大小。  
  
4.  使用 HTTP Post，发送页作为发送消息到合作伙伴的目标 URL 中的贸易合作伙伴协议中的操作 URL 或信号 URL 设置。  
  
5.  发送页等待 HTTP 响应。 当它收到响应时，它将其路由到 HTTP 适配器。  
  
6.  如果连接是异步的发送页将关闭连接，并处理过程完成。  
  
7.  如果连接是同步的则发送页将保持打开返回的消息进行连接。 收到消息后，它会执行相同的处理 RNIFReceive.aspx 页收到的消息执行、 将接收到的消息发送到 HTTP 适配器，然后关闭连接。  
  
## <a name="receive-aspx-page"></a>接收 ASPX 页  
 RNIFReceive.aspx 页通过 Internet 从合作伙伴接收 HTTP 消息。 它处理、 验证，然后删除 RNIF 头，并将消息提交到 HTTP 适配器。 接收页收到的消息必须与 RNIF HTTP 传输兼容。 接收页处理消息，如下所示：  
  
1.  响应方 RNIFReceive.aspx 页接收的消息从发起方。 该消息包含 MIME 头和上下边界。  
  
2.  接收页验证 MIME 标头。  
  
3.  接收页从消息中删除 MIME 头和边界。  
  
4.  接收页将消息发布到 HTTP 适配器使用 HTTP 接收位置。 接收页收到 HTTP 响应，并返回到发起方发送页的 HTTP 响应。  
  
5.  如果连接是异步的接收页将关闭连接。  
  
6.  如果连接是同步的则接收页将保持打开状态，等待返回的消息连接。  
  
7.  它从 HTTP 适配器接收返回的消息后，接收页执行相同的处理 RNIFSend.aspx 页，并将返回的消息发送到发起方发送页。 它收到 HTTP 响应后，它将关闭连接。  
  
## <a name="how-initiator-and-responder-aspx-pages-interact"></a>发起方和响应方 ASPX 页交互的方式  
 如果发起方和响应方使用[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]，发起方和响应方上的四个 ASPX 页交互以不同的方式具体取决于连接是同步还是异步、 和的消息是否是单操作还是双操作. 以下小节介绍了一整套的交互。  
  
 **双操作异步**  
  
 此方案涉及四个独立的 HTTP 连接，另一个用于每个步骤：  
  
1. 发起方发送页操作请求将消息的发送到响应方接收页。  
  
   > [!NOTE]
   >  步骤 2 和 3 下可能发生相反的顺序，根据系统负载。  
  
2. 响应方发送页请求信号将消息的发送到发起方接收页。  
  
3. 响应方发送页操作响应将消息的发送到发起方接收页。  
  
4. 发起方发送页响应信号将消息的发送到响应方接收页。  
  
   **单操作异步**  
  
   此方案涉及到两个独立的 HTTP 连接，另一个用于每个步骤。 请注意此方案包含的步骤 1 和 2 双操作异步方案。  
  
5. 发起方发送页操作请求将消息的发送到响应方接收页。  
  
6. 响应方发送页请求信号将消息的发送到发起方接收页。  
  
   **双操作同步**  
  
   此方案涉及一个 HTTP 连接：  
  
7. 发起方发送页操作请求将消息的发送到响应方接收页。  
  
8. 响应方接收页将操作响应消息 （或异常，如果问题） 在步骤 1 中使用的相同连接的发起方发送页。  
  
   **单操作同步**  
  
   此方案涉及一个 HTTP 连接：  
  
9. 发起方发送页操作请求将消息的发送到响应方接收页。  
  
10. 响应方接收页将请求信号消息 （或异常，如果问题） 相同的连接的发起方发送页。  
  
## <a name="see-also"></a>请参阅  
 [BTARN 中的消息处理](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)   
 [BTARN 接收管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)   
 [BTARN 发送管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)