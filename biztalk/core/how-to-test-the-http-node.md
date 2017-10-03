---
title: "如何测试 HTTP 节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP node, testing
- testing HTTP node
ms.assetid: f6881e8f-9f92-4312-bb5e-06bbfb9fe0bb
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2790a4e3fa0ff1ed9a9b9b0c2018108c9cbb1282
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-test-the-http-node"></a>如何测试 HTTP 节点
请按照以下步骤来测试 HTTP 节点。  
  
### <a name="to-test-the-http-node"></a>测试 HTTP 节点  
  
1.  在 PeopleSoft 企业中，导航到**PeopleTools**，**集成 Broker**，**监视器**，**监视器消息**。  
  
     ![](../core/media/psadapter-40-task-gatewaytestnode.gif "PSAdapter_40_Task_GatewayTestNode")  
  
2.  单击**节点状态**选项卡。  
  
3.  在**消息节点名称**字段中，输入`MSEXTERNAL`，然后单击**查找**图标。  
  
4.  下**消息节点名称**，选择**MSEXTERNAL**。  
  
     将显示一条消息，表明 PeopleSoft 正在通过 HTTP 进行通信。  
  
     ![](../core/media/psadapter-41-task-gatewaytestsuccess.gif "PSAdapter_41_Task_GatewayTestSuccess")  
  
     如果没有收到该消息，请验证以下内容：  
  
    1.  接收端口和节点间的 IP 地址和端口是否匹配。  
  
    2.  BizTalk Server 是否正在运行。  
  
## <a name="see-also"></a>另请参阅  
 [创建 PeopleSoft HTTP 主机和端口](../core/creating-a-peoplesoft-http-host-and-port.md)