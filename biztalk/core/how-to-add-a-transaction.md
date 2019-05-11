---
title: 如何添加事务 |Microsoft Docs
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
ms.openlocfilehash: 2734828dad1a236fa6bd599588f5b34094cfeb13
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387292"
---
# <a name="how-to-add-a-transaction"></a>如何添加事务
按照以下步骤添加事务。  
  
### <a name="to-add-a-transaction"></a>若要添加事务  
  
1. 单击**事务**选项卡。  
  
2. 单击**添加事务**。  
  
3. 单击**添加新值**。 输入以下信息，并单击**添加**。  
  
   1. **节点名称：** 验证是否属于这**MSEXTERNAL**。  
  
   2. **事务类型：** 验证是否属于这**出站异步**。  
  
   3. **请求消息：** 输入`LOCATION_SYNC`。  
  
   4. **请求消息版本：** 输入`VERSION_1`。  
  
      ![](../core/media/psadapter-38-task-gatewayaddtransaction.gif "PSAdapter_38_Task_GatewayAddTransaction")  
  
4. 上**交易详情**选项卡上，验证以下设置：  
  
   1. **状态：** 处于活动状态。  
  
   2. **路由：** 隐式。  
  
      ![](../core/media/psadapter-39-task-gatewaytransdetail.gif "PSAdapter_39_Task_GatewayTransDetail")  
  
5. 单击“保存” 。  
  
6. 单击**返回到事务列表**链接。  
  
    事务的事务列表中会出现。  
  
## <a name="see-also"></a>请参阅  
 [创建 PeopleSoft HTTP 主机和端口](../core/creating-a-peoplesoft-http-host-and-port.md)