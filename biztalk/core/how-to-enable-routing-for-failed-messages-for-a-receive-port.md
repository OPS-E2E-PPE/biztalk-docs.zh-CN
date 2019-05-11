---
title: 如何启用的路由失败消息的接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive ports, routing
- managing [receive ports], errors
- managing [receive ports], failed messages
- enabling, routing
- messages, failed messages
- routing, messages
- managing [receive ports], routing
- messages, routing
- receive ports, errors
- routing, receive ports
- routing, failed messages
- errors, receive ports
ms.assetid: 22366664-545d-4981-9bde-4df48b115002
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7410e7828acdf4968004e9a02bda4e4a26973260
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385122"
---
# <a name="how-to-enable-routing-for-failed-messages-for-a-receive-port"></a>如何启用的路由失败消息的接收端口
本主题介绍如何使用 BizTalk Server 管理控制台为接收端口处理的消息启用路由功能。 如果启用此选项时，BizTalk Server 将尝试将路由到某个订阅应用程序的处理失败的任何消息 （例如其他接收端口或业务流程计划）。 此选项时不启用 （默认值），BizTalk Server 挂起失败的消息，并生成一个否定确认 (NACK)。 有关管理失败的消息的背景信息，请参阅[使用失败消息路由](../core/using-failed-message-routing.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-enable-routing-for-failed-messages-for-a-receive-port"></a>若要为接收端口的失败消息启用路由功能  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开 BizTalk 组和 BizTalk 应用程序想要配置失败的消息路由的接收端口。  
  
3. 单击**接收端口**，右键单击接收端口，然后单击**属性**。  
  
4. 选择**失败消息启用路由功能**复选框，然后依次**确定**。  
  
## <a name="see-also"></a>请参阅  
 [管理接收端口](../core/managing-receive-ports.md)