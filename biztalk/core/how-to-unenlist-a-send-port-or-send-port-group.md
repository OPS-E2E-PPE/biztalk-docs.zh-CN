---
title: 如何取消登记发送端口或发送端口组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- unenlisting, send port groups
- send port groups, unenlisting
- managing [send ports], unenlisting
- managing [send port groups], unenlisting
- unenlisting, send ports
- send ports, unenlisting
ms.assetid: 3185adad-2efa-4abd-a532-77ae6c7b4c1d
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7dbd8a3a7c3450fcf36d66467cd95a38e39583dd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333779"
---
# <a name="how-to-unenlist-a-send-port-or-send-port-group"></a>如何取消登记发送端口或发送端口组
本主题介绍如何使用 BizTalk Server 管理控制台来取消登记发送端口或发送端口组。 取消登记发送端口或发送端口组可消除与该发送端口关联的所有订阅，或发送端口组。 你可以取消登记正在运行和已停止的发送端口或发送端口组。 自动取消登记发送端口或发送端口组将停止它。  
  
 例如，你可能想要取消登记发送端口或发送端口组，若要编辑其绑定，或者如果你想要删除发送端口或发送端口组从 BizTalk Server 环境。  
  
 无法取消登记发送端口组，或运行中的最后一个已登记的发送端口。 取消登记发送端口组不会更改它所包含的任何发送端口的状态。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-unenlist-a-send-port-or-send-port-group"></a>若要取消登记发送端口或发送端口组  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含发送端口或发送端口组想要的应用程序取消登记。  
  
3. 单击**发送端口**或**发送端口组**，右键单击发送端口或发送端口组，然后单击**取消登记**。  
  
## <a name="see-also"></a>请参阅  
 [管理发送端口和发送端口组](../core/managing-send-ports-and-send-port-groups.md)