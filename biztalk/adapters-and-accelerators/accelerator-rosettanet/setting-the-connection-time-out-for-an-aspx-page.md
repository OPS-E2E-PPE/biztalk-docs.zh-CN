---
title: 设置 ASPX 页的连接超时 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ASPX pages, connection time-out
- connections, time-out
ms.assetid: 61d9c996-caf4-48bd-bda7-52f2797a941b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8d28867e323a3fb7c3b50ab787b31b19c32c36e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281836"
---
# <a name="setting-the-connection-time-out-for-an-aspx-page"></a>设置 ASPX 页的连接超时值
当您使用用于同步消息的 ASPX 页时，必须增加 ASPX 页的连接超时值，以便它可以等待预期的消息。  
  
 增加连接超时的 ASPX 页中可以有意外的结果。 首先，它提高了拒绝服务攻击的风险和耗尽线程池的威胁。 其次，如果有太多 ASPX 页上的同步连接，系统可能会锁定。 因此，您必须增加连接超时值，而是小心以免增加的太多。  
  
 将连接超时值设置为 RosettaNet 组织所允许的最小。 有关详细信息的计时参数的合作伙伴接口流程 (PIP)，请参阅表 4-3:消息交换的控制，RosettaNet PIP 规范中。  
  
### <a name="to-set-the-connection-time-out-for-the-aspx-page"></a>设置 ASPX 页的连接超时值  
  
1.  单击**启动**，依次指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
2.  在 IIS 管理器中，展开本地计算机的节点，然后展开**网站**。  
  
3.  右键单击 **“默认的 Web 站点”**，然后单击 **“属性”**。  
  
4.  在默认网站属性对话框中上,**网站**选项卡上，在**连接超时**框中键入适当的值，，然后单击**确定**。  
  
## <a name="see-also"></a>请参阅  
 [编程指南](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)