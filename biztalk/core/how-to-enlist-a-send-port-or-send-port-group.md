---
title: 如何登记发送端口或发送端口组 |Microsoft Docs
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
ms.openlocfilehash: 2bb7ff544b1c6d5ae5559dd4b64348a92cacb56b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65337895"
---
# <a name="how-to-enlist-a-send-port-or-send-port-group"></a>如何登记发送端口或发送端口组
本主题介绍如何使用 BizTalk Server 管理控制台来登记发送端口或发送端口组。 登记发送端口或发送端口组的 BizTalk 主机相关联的发送端口或发送端口组，并创建发送端口或发送端口组的订阅。 如果发送端口组不包含发送端口，登记发送端口组不会创建任何订阅。 此外，登记发送端口组不会更改它所包含的任何发送端口的状态。  
  
> [!NOTE]
>  启动发送端口或发送端口组也会自动登记。 此外，默认情况下启动应用程序登记并启动所有项目。 有关详细信息，请参阅[如何启动发送端口或发送端口组](../core/how-to-start-a-send-port-or-send-port-group.md)。 另请参阅[如何启动和停止 BizTalk 应用程序](../core/how-to-start-and-stop-a-biztalk-application.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须以 BizTalk Server Administrators 组的成员的身份登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-enlist-a-send-port-or-send-port-group"></a>若要登记的发送端口或发送端口组  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含发送端口或发送端口组想要的应用程序登记。  
  
3. 单击**发送端口**或**发送端口组**，右键单击发送端口或发送端口组，然后单击**登记**。  
  
## <a name="see-also"></a>请参阅  
 [管理发送端口和发送端口组](../core/managing-send-ports-and-send-port-groups.md)