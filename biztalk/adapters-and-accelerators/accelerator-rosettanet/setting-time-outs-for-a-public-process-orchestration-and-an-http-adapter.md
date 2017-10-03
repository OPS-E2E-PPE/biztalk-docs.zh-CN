---
title: "为公共进程业务流程和 HTTP 适配器设置超时值 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- public processes, HTTP adapters
- public processes, orchestrations
- orchestrations, time-outs
- public processes, time-outs
- orchestrations, public-process orchestrations
- HTTP adapters, public processes
- HTTP adapters, time-outs
ms.assetid: 82fd64ac-6191-410c-94b3-8a3d1ff2611f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a8f7f15d01759704af6b6b3134c9d36f0e64f8e7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="setting-time-outs-for-a-public-process-orchestration-and-an-http-adapter"></a>为公共进程业务流程和 HTTP 适配器设置超时值
在同步方案中，如果将公用业务流程与 HTTP 适配器一起使用，则必须为它们设置相应的超时值。 业务流程的超时设置（执行时间）必须小于 HTTP 适配器的超时设置（请求超时值）。 这是因为如果 HTTP 适配器的设置较小，则适配器可能会在业务流程执行完之前发生超时。 这使适配器可以控制流程。 业务流程必须在流程的控制之下；因此，业务流程的超时设置必须较小。  
  
### <a name="to-set-the-time-out-setting-for-the-http-adapter"></a>设置 HTTP 适配器的超时设置  
  
1.  在 BizTalk 资源管理器中，展开**发送端口**，然后双击公共进程业务流程与使用 HTTP 发送端口。  
  
2.  在发送端口属性窗口中，单击省略号按钮 (**...**) 为**地址 (URI)**。  
  
3.  在 HTTP 传输属性窗口中，在常规的窗格中，在**请求超时 （秒）**框中，键入适当的值来表示超时值。此值必须大于**的执行时间**设置为相关合作伙伴接口过程 (PIP)。  
  
4.  单击**确定**，然后单击**确定**试。  
  
### <a name="to-set-the-time-out-setting-for-the-public-process-orchestration"></a>设置公用业务流程的超时设置  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft BizTalk\<版本 > Accelerator for RosettaNet**，然后单击**BizTalk Accelerator for RosettaNet 管理控制台**。  
  
2.  展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击**过程配置设置**。  
  
3.  右键单击你想要设置的超时设置，PIP，然后单击**属性**。  
  
4.  在 theProperties 对话框中，在**活动**选项卡上，在**的执行时间**框中，键入适当的值小于 HTTP 适配器超时设置，然后单击**确定**.  
  
## <a name="see-also"></a>另请参阅  
 [编程指南](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)