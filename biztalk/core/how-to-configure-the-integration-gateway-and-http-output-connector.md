---
title: "如何配置集成网关和 HTTP 输出连接器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Integration Gateway
- gateway nodes, creating
- HTTP Output Connector
ms.assetid: a02ee533-07a8-42fa-a72a-7e5359b18f40
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acfa52be85a664432af95af0ca292e9cc394c6ca
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-integration-gateway-and-http-output-connector"></a>如何配置集成网关和 HTTP 输出连接器
请按照下列步骤来配置集成网关和 HTTP 输出连接器。  
  
### <a name="to-create-and-configure-a-new-gateway-node"></a>若要创建和配置新的网关节点  
  
1.  在 Web 浏览器中，打开 PeopleSoft 应用程序。  
  
2.  找到**PeopleTools**，选择**集成 Broker**，然后选择**网关**。  
  
3.  在**搜索通过**字段中，键入`LOCAL`，然后单击**搜索**。  
  
     ![](../core/media/psadapter-31-task-gatewaysearch.gif "PSAdapter_31_Task_GatewaySearch")  
  
4.  输入`machine-name/PSIGW/PeopleSoftListeningConnector`到**网关 URL**条目。  
  
     ![](../core/media/psadapter-32-task-gatewayurl.gif "PSAdapter_32_Task_GatewayURL")  
  
5.  单击**刷新**，然后单击**保存**。  
  
6.  单击**属性**链接**HTTPTARGET**若要查看该 ID 的属性/值组合  
  
     您可以在这里，或者在节点定义设置 URL。 有关此讨论，在节点级别设置 URL。  
  
     ![](../core/media/psadapter-33-task-gatewaynodelevel.gif "PSAdapter_33_Task_GatewayNodeLevel")  
  
## <a name="see-also"></a>另请参阅  
 [创建 PeopleSoft HTTP 主机和端口](../core/creating-a-peoplesoft-http-host-and-port.md)