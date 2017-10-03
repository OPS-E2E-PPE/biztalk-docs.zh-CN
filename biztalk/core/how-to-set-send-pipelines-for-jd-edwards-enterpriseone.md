---
title: "如何设置发送管道的博士 Edwards EnterpriseOne |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, send pipelines
- send pipelines, configuring [JD Edwards EnterpriseOne adapters]
- adapters [JD Edwards EnterpriseOne adapters], configuring
- adapters [JD Edwards EnterpriseOne adapters], send pipelines
- JD Edwards EnterpriseOne adapters, configuring
ms.assetid: 4cfcecc1-febe-47c8-b75f-2b84defcdbbc
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8c9a6337195c8050afca1f12a015ec492db7f7ae
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-send-pipelines-for-jd-edwards-enterpriseone"></a>如何设置 JD Edwards EnterpriseOne 的发送管道
Microsoft BizTalk Adapter for 博士 Edwards EnterpriseOne 要求你选择**XMLTransmit**和**XMLReceive**为发送和接收管道分别。  
  
### <a name="to-set-pipelines"></a>若要设置管道  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。  
  
2.  右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。  
  
3.  在**发送端口属性**对话框框中，执行以下操作：  
  
    1.  例如，键入发送端口的名称`SendToJDEEnterpriseOne`。  
  
    2.  从**类型**下拉列表中，选择**JDE EnterpriseOne**。  
  
    3.  从**发送处理程序**下拉列表中，选择 URI。  
  
    4.  从发送管道下拉列表中选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。  
  
    5.  从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。  
  
4.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [创建博士 Edwards EnterpriseOne 发送处理程序](../core/creating-jd-edwards-enterpriseone-send-handlers.md)