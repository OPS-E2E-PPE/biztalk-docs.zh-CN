---
title: 连接超时值设置为 ASPX 页面 |Microsoft 文档
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
ms.openlocfilehash: 83e083b9f2f0262095e58b4ed9842627888773dd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207189"
---
# <a name="setting-the-connection-time-out-for-an-aspx-page"></a>ASPX 页设置连接超时
将 ASPX 页用于同步消息时，必须增加 ASPX 页的连接超时值，以便 ASPX 页可以等待所需的消息。  
  
 增加 ASPX 页的连接超时值可能会引起意外后果。 第一，这样做增加了遭受拒绝服务攻击和耗尽线程池的风险。 第二，如果 ASPX 页上有太多的同步连接，系统可能会锁定。 因此，当您必须增加连接超时值时，请注意不要增加的太多。  
  
 将连接超时值设置为 RosettaNet 组织所允许的最小值。 有关详细信息的计时参数为合作伙伴接口过程 (PIP)，请参阅表 4-3: RosettaNet PIP 规范中的消息交换控件。  
  
### <a name="to-set-the-connection-time-out-for-the-aspx-page"></a>设置 ASPX 页的连接超时  
  
1.  单击**启动**，指向**所有程序**，指向**管理工具**，然后单击**Internet Information Services (IIS) Manager**.  
  
2.  在 IIS 管理器中，展开本地计算机，节点，然后展开**网站**。  
  
3.  右键单击 **“默认的 Web 站点”**，然后单击 **“属性”**。  
  
4.  在默认 Web 站点属性对话框中，在**网站**选项卡上，在**连接超时**框中，键入适当的值，，然后单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [编程指南](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)