---
title: 如何终止挂起的业务流程实例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipelines, terminating [HAT]
- messages, saving [HAT]
- HAT, saving messages
- HAT, terminating pipelines
- HAT, terminiating orchestrations
- orchestrations, terminating [HAT]
ms.assetid: b5d44cce-b05c-47f9-9015-5b10c2312bf1
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e59442920c83b55e79692716ef5f5a447efd716
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333823"
---
# <a name="how-to-terminate-suspended-orchestration-instances"></a>如何终止挂起的业务流程实例
您可以终止任何挂起的业务流程实例或从查询结果或预览窗格，在 BizTalk Server 管理控制台的端口。  
  
> [!NOTE]
>  按序送达发送端口的每个实例可能具有与之关联的多条消息。 若要防止意外终止或数据丢失，请确保具有终止某一实例前查看所有此类关联。  
  
## <a name="prerequisites"></a>先决条件  
 您必须为要执行此过程的 BizTalk Server Operators 组的成员身份登录。  
  
### <a name="to-terminate-suspended-orchestration-instances"></a>若要终止挂起的业务流程实例  
  
1. 单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后单击 BizTalk 组。  
  
3. 在详细信息窗格中，单击**新查询**选项卡。  
  
4. 在中**查询表达式**组中，在**值**列中，选择**挂起服务实例**从下拉列表框。  
  
5. 执行以下操作之一：  
  
   - 若要终止单个实例，在**字段名**列，星号旁边的空下拉列表框中 (**\\**<em>)，选择 **服务名称</em>* 筛选器，然后在**值**列中，指定服务名称。  
  
   - 若要终止实例，请在**字段名**列，星号旁边的空下拉列表框中 (**\\**<em>)，选择 **结果分组依据</em>* ，然后在**值**列中，指定服务名称。  
  
6. 单击**运行查询**。  
  
7. 在查询结果列表中，右键单击业务流程实例或组以终止，然后单击所需的实例**终止的实例**或**终止实例**。  
  
## <a name="see-also"></a>请参阅  
 [调查业务流程、端口和消息失败](../core/investigating-orchestration-port-and-message-failures.md)