---
title: "如何为 PeopleSoft 企业设置管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- setting pipelines
- pipelines, setting
ms.assetid: 36914615-eac0-47b6-9e66-deeb40d21f10
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 69bebce2dadf0bb038b0e8c56ffa544ad02c78ff
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-pipelines-for-peoplesoft-enterprise"></a>如何设置 PeopleSoft Enterprise 的管道
用于 PeopleSoft Enterprise 的 Microsoft BizTalk 适配器要求您选择一个适当的管道。  
  
## <a name="setting-pipelines"></a>设置管道  
  
#### <a name="to-set-pipelines"></a>若要设置管道  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。  
  
2.  右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。  
  
3.  在**发送端口属性**对话框框中，执行以下操作：  
  
    1.  例如，键入发送端口的名称`SSOSendToPeopleSoft`。  
  
    2.  从**类型**下拉列表中，选择**PeopleSoft**。  
  
    3.  从**发送处理程序**下拉列表中，选择 URI。  
  
    4.  从发送管道下拉列表中选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。  
  
    5.  从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。  
  
4.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [创建 PeopleSoft 发送处理程序](../core/creating-peoplesoft-send-handlers.md)