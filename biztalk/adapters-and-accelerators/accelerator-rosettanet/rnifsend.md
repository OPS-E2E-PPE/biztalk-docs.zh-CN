---
title: RNIFSend | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 780f7446-56c5-40bf-95e2-25d0cff12f12
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92ad9b7c0318a028b6b2f98a75eca1484014b305
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65282236"
---
# <a name="rnifsend"></a>RNIFSend
此示例提供了一个有效的 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFSend.aspx 文件准备供 RNIF 处理的消息并将消息发送到响应方的 RNIFReceive.aspx 页。 可以自定义 ASPX 页后，可以执行以下操作：  
  
- 添加或删除性能计数器  
  
- 将功能添加到页上，如向数据库写入数据或自定义跟踪功能  
  
- 向页面添加验证  
  
  此示例位于*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\WebApplication\RNIFSender。  
  
## <a name="demonstrates"></a>演示  
 此示例演示如何准备供 RNIF 处理，包括以下传出消息：  
  
-   验证 MIME 标头的数据  
  
-   将 MIME 头和 MIME 边界添加到消息  
  
-   将消息发送到合作伙伴的 RNIFReceive.aspx  
  
-   处理返回的信号消息  
  
## <a name="see-also"></a>请参阅  
 [发送和接收 ASPX 页](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md)   
 [Web 应用程序示例](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)