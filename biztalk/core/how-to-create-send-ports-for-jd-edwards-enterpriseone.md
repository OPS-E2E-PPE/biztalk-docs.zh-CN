---
title: "如何为博士 Edwards EnterpriseOne 创建发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- JD Edwards EnterpriseOne adapters, send ports
- send ports, creating [JD Edwards EnterpriseOne adapters]
- adapters [JD Edwards EnterpriseOne adapters], send ports
- send ports, JD Edwards EnterpriseOne adapters
- creating, send ports [JD Edwards EnterpriseOne adapters]
ms.assetid: 687f9207-ad3e-41ea-8640-5b9b6efbc14e
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36a3e8d2d3e8e1db230a03d9c4a0351d3a0f8394
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-send-ports-for-jd-edwards-enterpriseone"></a>如何创建 JD Edwards EnterpriseOne 的发送端口
使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 创建发送端口。  
  
### <a name="to-create-a-send-port"></a>创建发送端口的步骤  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft BizTalk Server**，然后单击**BizTalk Server 管理**。  
  
2.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**，然后展开你想要创建发送端口的应用程序。  
  
3.  右键单击**发送端口**单击**新建**，然后单击**静态请求-响应端口**。  
  
4.  在**发送端口属性**对话框框中，执行以下操作：  
  
    -   在**名称**框中，键入发送端口名称 (例如， `SendToJDE`)。  
  
    -   从**类型**下拉列表中，选择**JDEdwards**。  
  
    -   从**发送处理程序**下拉列表中，选择发送处理程序地址。  
  
5.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [创建博士 Edwards EnterpriseOne 发送处理程序](../core/creating-jd-edwards-enterpriseone-send-handlers.md)