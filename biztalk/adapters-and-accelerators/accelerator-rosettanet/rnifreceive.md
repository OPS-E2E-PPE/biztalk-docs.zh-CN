---
title: RNIFReceive |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cf1253b0-ceca-4e7a-91ed-3837bd904472
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d54b66c42fae286ec748ef560c461a22124165b0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991766"
---
# <a name="rnifreceive"></a>RNIFReceive
此示例提供了一个有效的 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFReceive.aspx 文件接收 RNIF 消息，并使其准备好以供处理[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]公用流程。 你可以通过自定义 ASPX 页来执行以下操作：  
  
- 添加或删除性能计数器  
  
- 向该页添加功能，例如，将数据写入数据库或自定义跟踪功能  
  
- 向该页添加验证功能  
  
  此示例位于*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\WebApplication\RNIFReceiver。  
  
## <a name="demonstrates"></a>演示  
 此示例演示如何为公用流程准备传入消息，演示内容包括以下几个操作：  
  
-   从合作伙伴的 RNIFSend.aspx 接收消息  
  
-   验证 MIME 头  
  
-   从消息中删除 MIME 头和边界  
  
-   将消息路由到合作伙伴的 RNIFReceive.aspx  
  
-   返回信号消息  
  
## <a name="see-also"></a>请参阅  
 [发送和接收 ASPX 页](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md)   
 [Web 应用程序示例](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)