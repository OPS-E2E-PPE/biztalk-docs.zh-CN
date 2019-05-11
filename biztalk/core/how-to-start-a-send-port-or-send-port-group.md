---
title: 如何启动发送端口或发送端口组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- starting, send port groups
- starting, send ports
- managing [send port groups], starting
- managing [send ports], starting
- send port groups, starting
- send ports, starting
ms.assetid: f17c0b7c-cad7-4c5e-a08c-3ebf838faa54
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1749862ee78c549d3aa3fd79a62eedd1ecba144
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334041"
---
# <a name="how-to-start-a-send-port-or-send-port-group"></a>如何启动发送端口或发送端口组
本主题介绍如何使用 BizTalk Server 管理控制台启动发送端口或发送端口组。 必须启动发送端口或发送端口组，然后才能处理消息。 如果启动某个已取消登记的发送端口或发送端口组，BizTalk 将登记发送端口或发送端口组，然后再启动它。 发送端口组必须包含至少一个发送端口处于登记状态，然后才能启动发送端口组。 启动和停止发送端口组不会影响它所包含的任何发送端口的状态。  
  
> [!NOTE]
>  默认情况下，启动 BizTalk 应用程序启动的所有项目，它包含。 有关详细信息，请参阅[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须以 BizTalk Server Operators 组或 BizTalk Server Administrators 组的成员的身份登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-start-a-send-port-or-send-port-group"></a>若要启动的发送端口或发送端口组  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含发送端口或发送端口组想要的应用程序开始日期。  
  
3. 单击**发送端口**或**发送端口组**，右键单击发送端口或发送端口组，然后单击**启动**。  
  
## <a name="see-also"></a>请参阅  
 [管理发送端口和发送端口组](../core/managing-send-ports-and-send-port-groups.md)