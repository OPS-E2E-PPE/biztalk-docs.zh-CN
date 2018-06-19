---
title: 如何添加事务 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adding, transactions
- transactions, adding
ms.assetid: 25385c20-3025-4cf1-bc1f-ef266e081bad
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 24c67a9c76ae87f2355bb0ea4638d3bd156cda6e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246813"
---
# <a name="how-to-add-a-transaction"></a>如何添加事务
请按照以下步骤添加事务。  
  
### <a name="to-add-a-transaction"></a>添加事务  
  
1.  单击**事务**选项卡。  
  
2.  单击**添加事务**。  
  
3.  单击**添加新值**。 输入以下信息，，然后单击**添加**。  
  
    1.  **节点名称：** 验证，这是**MSEXTERNAL**。  
  
    2.  **事务类型：** 验证，这是**出站异步**。  
  
    3.  **请求消息：** 输入`LOCATION_SYNC`。  
  
    4.  **请求消息版本：** 输入`VERSION_1`。  
  
     ![](../core/media/psadapter-38-task-gatewayaddtransaction.gif "PSAdapter_38_Task_GatewayAddTransaction")  
  
4.  上**事务详细信息**选项卡上，验证以下设置：  
  
    1.  **状态：** 活动。  
  
    2.  **路由：** 隐式。  
  
     ![](../core/media/psadapter-39-task-gatewaytransdetail.gif "PSAdapter_39_Task_GatewayTransDetail")  
  
5.  单击 **“保存”**。  
  
6.  单击**返回到事务列表**链接。  
  
     事务会出现在事务列表中。  
  
## <a name="see-also"></a>另请参阅  
 [创建 PeopleSoft HTTP 主机和端口](../core/creating-a-peoplesoft-http-host-and-port.md)