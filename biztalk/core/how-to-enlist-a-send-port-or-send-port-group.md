---
title: 如何发送端口或发送端口组中登记 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- enlisting, send port groups
- enlisting, send ports
- send port groups, enlisting
- send ports, enlisting
- managing [send ports], enlisting
- managing [send port groups], enlisting
ms.assetid: d4298b8e-7dc7-4382-af86-c4db0982b7e0
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb42a4ceaa88ca3d04b5dfb6d6d3afc11847421a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254469"
---
# <a name="how-to-enlist-a-send-port-or-send-port-group"></a>如何登记发送端口或发送端口组
本主题将介绍如何使用 BizTalk Server 管理控制台登记发送端口或发送端口组。 登记发送端口或发送端口组将把发送端口或发送端口组与 BizTalk 主机相关联，并为发送端口或发送端口组创建订阅。 如果发送端口组不包含发送端口，登记发送端口组将不会创建任何订阅。 此外，登记发送端口组不会改变其包含的任何发送端口的状态。  
  
> [!NOTE]
>  启动发送端口或发送端口组也会自动登记该发送端口或发送端口组。 此外，默认情况下，启动应用程序会登记并启动它的所有项目。 有关详细信息，请参阅[如何启动发送端口或发送端口组](../core/how-to-start-a-send-port-or-send-port-group.md)。 另请参阅[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，则必须以 BizTalk Server Administrators 组成员的身份登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-enlist-a-send-port-or-send-port-group"></a>登记发送端口或发送端口组  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含发送端口或发送到所需的端口组的应用程序登记。  
  
3.  单击**发送端口**或**发送端口组**，右键单击发送端口或发送端口组，然后单击**Enlist**。  
  
## <a name="see-also"></a>另请参阅  
 [管理发送端口和发送端口组](../core/managing-send-ports-and-send-port-groups.md)