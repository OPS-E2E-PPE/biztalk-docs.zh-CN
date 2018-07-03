---
title: RNIFSend |Microsoft Docs
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
ms.openlocfilehash: 0d9aca64afee9ed979b2eee58a5f2bdafb25b461
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011598"
---
# <a name="rnifsend"></a>RNIFSend
此示例提供了一个有效的 Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] RNIFSend.aspx 文件准备供 RNIF 处理的消息并将消息发送到响应方的 RNIFReceive.aspx 页。 你可以通过自定义 ASPX 页来执行以下操作：  
  
- 添加或删除性能计数器  
  
- 向该页添加功能，例如，将数据写入数据库或自定义跟踪功能  
  
- 向该页添加验证功能  
  
  此示例位于*\<驱动器\>*: \Program Files\Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\WebApplication\RNIFSender。  
  
## <a name="demonstrates"></a>演示  
 此示例演示如何准备供 RNIF 处理的传出消息，包括以下内容：  
  
-   验证 MIME 头的数据  
  
-   向消息中添加 MIME 头和 MIME 边界  
  
-   将消息发送到合作伙伴的 RNIFReceive.aspx  
  
-   处理返回的信号消息  
  
## <a name="see-also"></a>请参阅  
 [发送和接收 ASPX 页](../../adapters-and-accelerators/accelerator-rosettanet/send-and-receive-aspx-pages.md)   
 [Web 应用程序示例](../../adapters-and-accelerators/accelerator-rosettanet/web-application-samples.md)