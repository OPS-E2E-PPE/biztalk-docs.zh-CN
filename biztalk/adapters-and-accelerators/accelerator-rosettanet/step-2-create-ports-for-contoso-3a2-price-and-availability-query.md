---
title: 步骤 2： 为 Contoso 3A2 价格和可用性查询响应方案中使用 BizTalk 资源管理器创建端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating ports
ms.assetid: e0b12a96-e799-47ac-8293-7de10662bdf0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64101a31b1d1ea9c7af00471c5d764a1d8cfe598
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22210141"
---
# <a name="step-2-creating-ports-for-the-contoso-3a2-price-and-availability-queryresponse-scenario"></a>步骤 2： 为 Contoso 3A2 价格和可用性查询/响应方案创建端口
在此步骤中，你可以创建使用 BizTalk Server 提供的 SQL 适配器的发送端口。 该 SQL 端口将用于向 Contoso ERP 系统发送 3A2 价格与可用性响应，及从 Contoso ERP 系统接收 3A2 价格与可用性响应。  
  
### <a name="to-configure-a-send-port-using-the-sql-adapter"></a>使用 SQL 适配器配置发送端口  
  
1.  在 Visual Studio 中，在**视图**菜单上，单击**BizTalk 资源管理器**。  
  
2.  在 BizTalk 资源管理器中，右键单击**发送端口**，然后单击**添加发送端口**。  
  
3.  在创建新发送端口对话框中，选择**静态请求-响应端口**从下拉列表，然后单击**确定**。  
  
4.  在静态请求-响应发送端口属性对话框中，在**名称**框中，键入**3A2SQLReqResponseSendPort**。  
  
5.  下的属性窗口中**常规**标题下，选择**SQL**作为**传输类型**。  
  
6.  在**地址 URI**框中，单击省略号按钮 (**...**).  
  
7.  在 SQL 传输属性对话框中，单击省略号按钮 (**...**) 旁边**连接字符串**框。  
  
8.  在数据链接属性对话框中，在**选择或输入服务器名称**框中，键入**localhost**。  
  
9. 选择**使用 Windows NT 集成安全性**。  
  
10. 在**选择服务器上的数据库**框中，选择**Contoso**，然后单击**确定**。  
  
11. 在 SQL 传输属性对话框中，在**文档目标 Namespace**框中，键入**http://Contoso.com/Price**。  
  
12. 在**响应文档根元素名称**框中，键入**rootPriceResponse**，然后单击**确定**。  
  
13. 在静态的请求-响应发送端口属性对话框的左窗格中，单击**发送**。  
  
14. 在静态请求-响应发送端口属性-配置-发送的常规对话框中，在**发送管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.XMLTransmit**。  
  
15. 在**接收管道**框中，选择**Microsoft.BizTalk.DefaultPipelines.XMLReceive**，然后单击**确定**。  
  
16. 在 BizTalk 资源管理器中，右键单击**3A2SQLReqResponseSendPort**，然后单击**Enlist**。 再次右键单击它，然后单击**启动**。  
  
## <a name="see-also"></a>另请参阅  
 [创建和修改 Contoso 私有过程](creating-and-modifying-the-private-process-for-contoso.md)