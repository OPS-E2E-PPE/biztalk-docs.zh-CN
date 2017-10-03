---
title: "如何设置发送管道 TIBCO 企业消息服务 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send pipelines
- setting send pipelines
- pipelines, send
ms.assetid: 6a84d874-4b4d-4b23-913f-f5c72af1e96e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d037782e2580d52c6609c3669e2805aae92ce9eb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-send-pipelines-for-tibco-enterprise-message-service"></a>如何设置 TIBCO Enterprise Message Service 的发送管道
用于 TIBCO Enterprise Message Service 的 Microsoft BizTalk 适配器要求您分别选择 XMLTransmit 和 XMLReceive 作为发送和接收管道。  
  
### <a name="to-set-pipelines"></a>若要设置管道  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。  
  
2.  右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。  
  
3.  在**发送端口属性**对话框框中，执行以下操作：  
  
    1.  例如，键入发送端口的名称`SendToTIBCOEMS`。  
  
    2.  从**类型**下拉列表中，选择**TIBCO EMS**。  
  
    3.  从**发送处理程序**下拉列表中，选择 URI。  
  
    4.  从发送管道下拉列表中选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。  
  
    5.  从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。  
  
4.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [如何设置 TIBCO 企业消息服务接收管道](../core/how-to-set-receive-pipelines-for-tibco-enterprise-message-service.md)