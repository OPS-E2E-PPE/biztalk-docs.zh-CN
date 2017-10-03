---
title: "如何创建接收端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, receive
- receive ports
- creating receive ports
ms.assetid: d390320e-12f1-4ead-b608-60bc1e273477
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1ca5727422fd7519443cc290d35d0c2e24d499f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-receive-ports"></a>如何创建接收端口
请按照下列步骤使用 Visual Studio 创建一个接收端口。  
  
### <a name="to-create-a-receive-port"></a>若要创建接收端口  
  
1.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。  
  
2.  右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。  
  
3.  在**接收端口属性**窗口，请在**常规**页上，执行以下操作：  
  
    1.  在**名称**字段中，键入`ReceiveFromTIBCORV`。  
  
    2.  在**身份验证**组框中，指定使用身份验证时处理消息的方式。  
  
    3.  选择**启用路由失败消息**复选框。  
  
4.  上**接收位置**页上，执行以下操作：  
  
    1.  单击 **“新建”**。  
  
    2.  在**接收位置**窗口，请在**常规**页上，键入**名称**的接收位置。  
  
    3.  从**类型**下拉列表中，选择传输类型，并从**接收处理程序**下拉列表中，选择的传输地址。  
  
    4.  从**接收管道**下拉列表中，选择接收管道。  
  
    5.  上**计划**页上，选择**开始日期**和**结束日期**限制接收的文档。  
  
    6.  选择**启用服务窗口**复选框。  
  
    7.  单击 **“确定”**。  
  
5.  上**入站映射**页上，选择转换所选的端口上的文档的入站的映射。  
  
6.  上**跟踪**页上，选择所需的跟踪消息正文和跟踪消息属性。  
  
7.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [创建 TIBCO 会合接收处理程序](../core/creating-tibco-rendezvous-receive-handlers.md)