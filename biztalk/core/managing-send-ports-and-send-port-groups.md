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
ms.openlocfilehash: 6b3fe64a46ec4dd80d278e36f91406db0c431972
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37015750"
---
# <a name="manage-send-ports-and-send-port-groups"></a>管理发送端口和发送端口组

## <a name="overview"></a>概述
本部分介绍如何使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台创建、配置和管理 BizTalk 应用程序中的发送端口和发送端口组。 发送端口指定消息发送到的位置，以及接收响应的位置（可选）。 一条消息发送到发送端口，创建新的发送端口服务实例，这称为任何时候*服务实例*。  
  
 发送端口组是发送端口的逻辑分组。 消息发送到发送端口组后，会被路由到所有相关的发送端口。  有关发送端口和发送端口组的背景信息，请参阅[发送端口和发送端口组](../core/send-ports-and-send-port-groups.md)。  
  
> [!NOTE]
>  Microsoft Windows Management Instrumentation (WMI) 对象模型可用于创建和运行自动执行管理任务的脚本。 有关使用 WMI 的信息，请参阅**WMI 类引用** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
> 
> [!NOTE]
>  开发 BizTalk 应用程序时，开发人员可使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中的 BizTalk 设计工具（例如业务流程设计器）来创建和配置发送端口和发送端口组。 有关详细信息，请参阅[业务流程中使用端口](../core/using-ports-in-orchestrations.md)。  
  
## <a name="next-steps"></a>后续步骤
  
-   [创建和配置发送端口](../core/creating-and-configuring-send-ports.md)  
  
-   [创建和配置发送端口组](../core/creating-and-configuring-send-port-groups.md)  
  
-   [登记发送端口或发送端口组](../core/how-to-enlist-a-send-port-or-send-port-group.md)  
  
-   [取消登记发送端口或发送端口组](../core/how-to-unenlist-a-send-port-or-send-port-group.md)  
  
-   [启动发送端口或发送端口组](../core/how-to-start-a-send-port-or-send-port-group.md)  
  
-   [停止发送端口或发送端口组](../core/how-to-stop-a-send-port-or-send-port-group.md)