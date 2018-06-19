---
title: 发送和接收 ASPX 页 |Microsoft 文档
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
ms.openlocfilehash: 0782c421dfe771cd024b5ce4df893e2aaa45721d
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
ms.locfileid: "25967443"
---
# <a name="send-and-receive-aspx-pages"></a>发送和接收 ASPX 页
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] ASPX 页是间的直接接口[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]和 Internet。 两个 ASPX 页分别是接收页 (RNIFReceive.aspx) 和发送页 (RNIFSend.aspx)。 每个 ASPX 页都是相应 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管道的扩展。 该管道需要 ASPX 页来处理 RosettaNet 实现框架 (RNIF) 头。 管道执行大部分 HTTP 处理，而每个 ASPX 页执行 RNIF 头的 HTTP 处理。 这些 ASPX 页对 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] HTTP 适配器的功能进行了补充。  
  
 每个 ASPX 页都是一个没有用户界面的 ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web 应用程序。 它们使用 ASP[!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] Web 安全以确保与外部参与方的安全连接。 这些 ASPX 页提供了一个层，您可以在该层实现容错、可伸缩性和高可用性的服务。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 安装程序在部署了 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 的每台计算机上安装一个 RNIFSend.aspx 页和一个 RNIFReceive.aspx 页。 当发起方或响应方与贸易合作伙伴交换消息时，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 使用 ASPX 页将消息发送到该贸易伙伴 URL，或从该贸易伙伴 URL 接收消息。 如果发起方和响应方都使用 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]，则发起方的两个 ASPX 页将与响应方的两个 ASPX 页交换消息。 有关详细信息，请参阅下面的子节“发起方和响应方 ASPX 页的交互方式”。  
  
## <a name="send-aspx-page"></a>发送 ASPX 页  
 RNIFSend.aspx 页从 BizTalk HTTP 适配器接收消息。 该页创建 RNIF 头并将其添加到消息中，然后通过 Internet 将消息发送给合作伙伴。 HTTP 适配器使用以下命令调用 RNIFSend.aspx：  
  
```  
http://localhost:<port number>/RNIFSend.aspx?<query string>  
```  
  
 查询字符串包括下列数据，分别是发送页向合作伙伴发送消息所需数据，以及合作伙伴处理消息所需数据：  
  
-   贸易合作伙伴 URL: http://www。\<*地址*\>.com/RNIFReceive.aspx  
  
-   响应类型： 同步或异步  
  
-   RNIF 版本： 1.1 或 2.0。  
  
 BizTalk HTTP 适配器将 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 发送管道生成的一个 MIME 消息发送到发起方的 RNIFSend.aspx 页。 RNIFSend.aspx 按以下方式处理该消息：  
  
1.  发送页对消息进行验证。  
  
2.  发送页根据消息的内容类型、长度、ID 和多用途 Internet 邮件扩展 (MIME) 版本创建 MIME 头。 该页将 MIME 头和 MIME 上下边界添加到消息中。  
  
3.  对于 RNIF 2.01，发送页按以下方式设置 HTTP 标头的属性：  
  
    1.  它将 X-RN-Version 属性设置为流程配置设置的“版本”属性中输入的版本。  
  
    2.  它将 X-RN-ResponseType 属性设置为 sync 或 async，具体取决于流程配置设置中 IsSynchronous 属性的设置。  
  
    3.  它将 Content-Length 属性设置为完整消息的大小。  
  
4.  发送页使用 HTTP Post 按照贸易合作伙伴协议中操作 URL 或信号 URL 设置设定的位置将消息发送到合作伙伴的目标 URL。  
  
5.  然后发送页等待 HTTP 响应。 接收到响应后，它将该响应路由到 HTTP 适配器。  
  
6.  如果连接是异步的，发送页将关闭连接，处理过程完成。  
  
7.  如果连接是同步的，发送页将保持连接的开通以接收返回的消息。 发送页在收到消息以后执行的处理与 RNIFReceive.aspx 对所收到消息的处理相同，然后，发送页将收到的消息发送到 HTTP 适配器，最后关闭连接。  
  
## <a name="receive-aspx-page"></a>接收 ASPX 页  
 RNIFReceive.aspx 页通过 Internet 接收合作伙伴的 HTTP 消息。 该页处理、验证并删除 RNIF 头，然后将该消息提交到 HTTP 适配器。 接收页收到的消息必须与 RNIF HTTP 传输兼容。 接收页处理消息的方式如下：  
  
1.  响应方 RNIFReceive.aspx 页接收来自发起方消息， 该消息包含 MIME 头和上下边界。  
  
2.  接收页验证 MIME 头。  
  
3.  接收页删除消息中的 MIME 头和边界。  
  
4.  接收页使用 HTTP 接收位置将消息发布到 HTTP 适配器， 并接收 HTTP 响应，然后将其返回给发起方发送页。  
  
5.  如果连接是异步的，接收页将关闭连接。  
  
6.  如果连接是同步的，接收页将保持连接的开通状态以等待返回的消息。  
  
7.  接收页在收到 HTTP 适配器返回的消息以后，执行与 RNIFSend.aspx 页相同的处理，然后将返回消息发送给发起方发送页； 在收到 HTTP 响应以后，关闭连接。  
  
## <a name="how-initiator-and-responder-aspx-pages-interact"></a>发起方 ASPX 页和响应方 ASPX 页的交互方式  
 如果发起方和响应方都使用 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]，则双方的四个 ASPX 页将根据连接是同步还是异步、消息是单操作还是双操作分别进行不同的交互。 以下各个子节对全部交互方案进行说明。  
  
 **异步双操作**  
  
 此方案涉及四个单独的 HTTP 连接，每步一个连接：  
  
1.  发起方发送页将操作请求消息发送到响应方接收页。  
  
    > [!NOTE]
    >  根据系统负载情况，下面的步骤 2 和步骤 3 的次序可能会颠倒。  
  
2.  响应方发送页将请求信号消息发送到发起方接收页。  
  
3.  响应方发送页将操作响应消息发送到发起方接收页。  
  
4.  发起方发送页将响应信号消息发送到响应方接收页。  
  
 **异步单操作**  
  
 此方案涉及两个单独的 HTTP 连接，每步一个连接。 请注意，此方案由双操作异步方案的步骤 1 和步骤 2 组成。  
  
1.  发起方发送页将操作请求消息发送到响应方接收页。  
  
2.  响应方发送页将请求信号消息发送到发起方接收页。  
  
 **同步双操作**  
  
 此方案涉及一个 HTTP 连接：  
  
1.  发起方发送页将操作请求消息发送到响应方接收页。  
  
2.  响应方接收页将操作响应消息（如果出现问题则为异常消息）发送到与步骤 1 所用连接相同的发起方发送页。  
  
 **同步单操作**  
  
 此方案涉及一个 HTTP 连接：  
  
1.  发起方发送页将操作请求消息发送到响应方接收页。  
  
2.  响应方接收页将请求信号消息（如果出现问题则为异常消息）发送到同一连接的发起方发送页。  
  
## <a name="see-also"></a>另请参阅  
 [消息处理在 BTARN](../../adapters-and-accelerators/accelerator-rosettanet/message-processing-in-btarn.md)   
 [BTARN 接收管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-receive-pipeline.md)   
 [BTARN 发送管道](../../adapters-and-accelerators/accelerator-rosettanet/btarn-send-pipeline.md)