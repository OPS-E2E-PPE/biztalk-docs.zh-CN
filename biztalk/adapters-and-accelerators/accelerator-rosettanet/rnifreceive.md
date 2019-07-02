---
title: RNIFReceive | Microsoft Docs
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
ms.openlocfilehash: b2c949f87f74881da64475c74c6e26099359f925
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282250"
---
# <a name="rnifreceive"></a>RNIFReceive
此示例提供了一个有效的 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFReceive.aspx 文件接收 RNIF 消息，并使其准备好以供处理[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]公用流程。 可以自定义 ASPX 页后，可以执行以下操作：  
  
- 添加或删除性能计数器  
  
- 将功能添加到页上，如向数据库写入数据或自定义跟踪功能  
  
- 向页面添加验证  
  
  此示例位于 *\<驱动器\>* : \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\WebApplication\RNIFReceiver。  
  
## <a name="demonstrates"></a>演示  
 此示例演示如何准备传入消息的公用流程，其中包括：  
  
-   从合作伙伴的 RNIFSend.aspx 接收消息  
  
-   验证 MIME 头  
  
-   从消息中删除 MIME 头和边界  
  
-   将消息路由到合作伙伴的 RNIFReceive.aspx  
  
-   返回信号消息  
  
## <a name="see-also"></a>请参阅  
 [发送和接收 ASPX 页](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md)   
 [Web 应用程序示例](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)