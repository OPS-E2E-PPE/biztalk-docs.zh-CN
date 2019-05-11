---
title: 设置公用业务流程和 HTTP 适配器的超时值 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70dd783e805116b24e224886e02d0f46fe2edfed
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281821"
---
# <a name="setting-time-outs-for-a-public-process-orchestration-and-an-http-adapter"></a>设置公用业务流程和 HTTP 适配器的超时值
当使用 HTTP 适配器在同步方案中使用公用业务流程时，必须在相应地为每个设置的超时。 业务流程 （执行时间） 的超时设置必须小于 HTTP 适配器 （请求超时） 的超时值。 这是因为如果 HTTP 适配器设置为较小，则适配器可能会超时后，业务流程。 这使适配器可以控制的过程。 业务流程必须掌控的进程;因此，其超时设置必须为较小。  
  
### <a name="to-set-the-time-out-setting-for-the-http-adapter"></a>设置 HTTP 适配器的超时设置  
  
1.  在 BizTalk 浏览器中，展开**发送端口**，然后双击与公用业务流程使用的 HTTP 发送端口。  
  
2.  在发送端口属性窗口中，单击省略号按钮 (**...**) 用于**地址 (URI)**。  
  
3.  在常规窗格中的 HTTP 传输属性窗口中**请求超时 （秒）** 框中，键入适当的值来表示超时值。此值必须大于**执行时间**设置为相关合作伙伴接口流程 (PIP)。  
  
4.  单击**确定**，然后单击**确定**试。  
  
### <a name="to-set-the-time-out-setting-for-the-public-process-orchestration"></a>设置公用业务流程的超时设置  
  
1. 单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for RosettaNet**，然后单击**BizTalk Accelerator for RosettaNet 管理控制台**。  
  
2. 展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击**流程配置设置**。  
  
3. 右键单击你想要设置超时设置的 PIP，然后单击**属性**。  
  
4. 在属性对话框中，在**活动**选项卡上，在**执行时间**框中，键入适当的值小于 HTTP 适配器超时设置，然后依次**确定**.  
  
## <a name="see-also"></a>请参阅  
 [编程指南](../../adapters-and-accelerators/accelerator-rosettanet/programming-guide2.md)