---
title: "如何为 TIBCO 会合创建发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating send ports
- ports, send
- send ports, creating
ms.assetid: 0c8d9fdc-b273-4876-9f93-b5a85539a3c1
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7d0b6e7dbb1a3b32979c94ec1af9483bd9fcb7cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-tibco-rendezvous"></a>如何创建 TIBCO Rendezvous 的发送端口
请按照以下步骤，使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 创建一个发送端口。  
  
### <a name="to-create-a-send-port"></a>创建发送端口的步骤  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。  
  
2.  右键单击**发送端口**，指向**新建**，然后单击**静态请求-响应发送端口**。  
  
3.  在**发送端口属性**对话框框中，执行以下操作：  
  
    1.  例如，键入发送端口的名称`SendToTIBCORV`。  
  
    2.  从**类型**下拉列表中，选择**TIBCO 会合**。  
  
    3.  从**发送处理程序**下拉列表中，选择 URI。  
  
    4.  从发送管道下拉列表中选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。  
  
    5.  从**接收管道**下拉列表中，选择**Microsoft.BizTalk.DefaultPiplelines.XMLReceive**。  
  
    6.  单击**配置**配置发送端口。  
  
4.  在**TIBCO 会合传输属性**对话框框中，执行以下操作：  
  
    1.  输入属性。  
  
         您不必设置登录信息。  
  
    2.  在列表中，选择 SSO 关联应用程序创建的用来表示 TIBCO 会合系统。  
  
    3.  有关**使用 SSO**，选择**是**。  
  
    4.  单击 **“确定”**。  
  
5.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [创建 TIBCO 会合发送处理程序](../core/creating-tibco-rendezvous-send-handlers.md)