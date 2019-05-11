---
title: 管理发送端口和发送端口组 |Microsoft Docs
description: 链接来创建、 配置、 登记、 取消登记，以及开始和停止 BizTalk Server 中的发送端口
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db45f9f9-b32a-4b9c-a3bf-8c271d0f0cf9
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3512a9ab6d3ef7995ee576be0528878588753c8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380188"
---
# <a name="manage-send-ports-and-send-port-groups"></a>管理发送端口和发送端口组

## <a name="overview"></a>概述
本部分说明了使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台来创建、 配置和管理发送端口和 BizTalk 应用程序中的发送端口组。 发送端口指定的位置向其发送消息，并且可以选择收到的响应。 一条消息发送到发送端口，创建新的发送端口服务实例，这称为任何时候*服务实例*。  
  
 发送端口组是发送端口的逻辑分组。 当消息发送到发送端口组时，则将它路由到的所有相关的发送端口。  有关发送端口和发送端口组的背景信息，请参阅[发送端口和发送端口组](../core/send-ports-and-send-port-groups.md)。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
> 
> [!NOTE]
>  在开发 BizTalk 应用程序，开发人员可以使用中的 BizTalk 设计工具[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，如业务流程设计器中，若要创建和配置发送端口和发送端口组。 有关详细信息，请参阅[业务流程中使用端口](../core/using-ports-in-orchestrations.md)。  
  
## <a name="next-steps"></a>后续步骤
  
-   [创建和配置发送端口](../core/creating-and-configuring-send-ports.md)  
  
-   [创建和配置发送端口组](../core/creating-and-configuring-send-port-groups.md)  
  
-   [登记发送端口或发送端口组](../core/how-to-enlist-a-send-port-or-send-port-group.md)  
  
-   [取消登记发送端口或发送端口组](../core/how-to-unenlist-a-send-port-or-send-port-group.md)  
  
-   [启动发送端口或发送端口组](../core/how-to-start-a-send-port-or-send-port-group.md)  
  
-   [停止发送端口或发送端口组](../core/how-to-stop-a-send-port-or-send-port-group.md)