---
title: 如何测试 HTTP 节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP node, testing
- testing HTTP node
ms.assetid: f6881e8f-9f92-4312-bb5e-06bbfb9fe0bb
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27e3ebdc1c75ba0e42e5af8a57e194d3ab363753
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333882"
---
# <a name="how-to-test-the-http-node"></a>如何测试 HTTP 节点
请按照以下步骤来测试 HTTP 节点。  
  
### <a name="to-test-the-http-node"></a>若要测试 HTTP 节点  
  
1.  在 PeopleSoft Enterprise 中，导航到**PeopleTools**， **Integration Broker**，**监视器**，**监视器消息**。  
  
     ![](../core/media/psadapter-40-task-gatewaytestnode.gif "PSAdapter_40_Task_GatewayTestNode")  
  
2.  单击**节点状态**选项卡。  
  
3.  在中**消息节点名称**字段中，输入`MSEXTERNAL`，然后单击**查找**图标。  
  
4.  下**消息节点名称**，选择**MSEXTERNAL**。  
  
     显示消息，指示 PeopleSoft 通过 HTTP 进行通信。  
  
     ![](../core/media/psadapter-41-task-gatewaytestsuccess.gif "PSAdapter_41_Task_GatewayTestSuccess")  
  
     如果未收到消息，确认下列条件：  
  
    1.  接收端口和节点之间的 IP 地址和端口匹配。  
  
    2.  BizTalk Server 正在运行。  
  
## <a name="see-also"></a>请参阅  
 [创建 PeopleSoft HTTP 主机和端口](../core/creating-a-peoplesoft-http-host-and-port.md)