---
title: 如何创建新的网关节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- gateway nodes, creating
ms.assetid: e7c5f9a7-a58e-4661-9cb5-2414e31a57a3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5549317c45fbb431155eb3fab3e757c519956cc8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385578"
---
# <a name="how-to-create-a-new-gateway-node"></a>如何创建新的网关节点
按照以下步骤来创建和配置新的网关节点在 PeopleSoft Enterprise。  
  
### <a name="to-create-and-configure-a-new-gateway-node"></a>若要创建和配置新的网关节点  
  
1. 在 PeopleSoft，左面板中，单击**节点定义**链接。  
  
2. 单击**添加新值**选项卡。  
  
3. 在中**节点名称**字段中，输入`MSEXTERNAL`，然后单击**添加**。  
  
4. 单击**节点**选项卡，然后输入以下信息：  
  
   1. **说明：** 输入节点的说明。  
  
   2. **节点类型：** 选择**外部**。  
  
   3. **路由类型：** 选择**隐式**。  
  
      ![](../core/media/psadapter-34-task-gatewaynodeconnector.gif "PSAdapter_34_Task_GatewayNodeConnector")  
  
5. 单击**连接器**选项卡，然后输入以下信息：  
  
   1. **网关 ID:** 输入`LOCAL`。  
  
   2. **连接器 ID:** 输入`HTTPTARGET`。  
  
      ![](../core/media/psadapter-35-task-gatewayhttptarget.gif "PSAdapter_35_Task_GatewayHTTPTarget")  
  
6. 单击**查找**图标。  
  
7. 下**连接器 ID**，单击**HTTPTARGET**链接。  
  
    ![](../core/media/psadapter-36-task-gatewayconnectorid.gif "PSAdapter_36_Task_GatewayConnectorID")  
  
8. 上**属性**选项卡上，输入以下信息：  
  
   1.  **标头：** 输入`Y`。  
  
   2.  **HTTPPROPERTY:** 输入`POST`。  
  
   3.  **PrimaryURL:** 输入的 IP 地址和端口的目标计算机 （开发计算机）。  
  
   > [!NOTE]
   >  **接收端口**之前设置。  
  
    ![](../core/media/psadapter-37-task-gatewaynodereceiveport.gif "PSAdapter_37_Task_GatewayNodeReceivePort")  
  
## <a name="see-also"></a>请参阅  
 [创建 PeopleSoft HTTP 主机和端口](../core/creating-a-peoplesoft-http-host-and-port.md)