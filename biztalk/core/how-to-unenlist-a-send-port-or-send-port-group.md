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
ms.openlocfilehash: ee33b2ea9711b19e23067b164ecef9084541ba87
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967742"
---
# <a name="how-to-unenlist-a-send-port-or-send-port-group"></a>如何取消登记发送端口或发送端口组
本主题将介绍如何使用 BizTalk Server 管理控制台来取消登记发送端口或发送端口组。 取消登记发送端口或发送端口组可取消与该发送端口或发送端口组相关联的所有订阅。 正在运行的和已停止的发送端口或发送端口组都可以取消登记。 取消登记发送端口或发送端口组将自动停止端口或端口组。  
  
 例如，您可能需要取消登记发送端口或发送端口组以编辑其绑定，或者取消登记发送端口或发送端口组以将其从 BizTalk Server 环境中删除。  
  
 您不能取消登记发送端口组中最近登记或运行的发送端口。 取消登记发送端口组不会改变其包含的任何发送端口的状态。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-unenlist-a-send-port-or-send-port-group"></a>取消登记发送端口或发送端口组  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开**BizTalk Server 管理**，展开 BizTalk 组，展开**应用程序**，然后展开包含发送端口或发送端口组想要的应用程序取消登记。  
  
3. 单击**发送端口**或**发送端口组**，右键单击发送端口或发送端口组，然后单击**取消登记**。  
  
## <a name="see-also"></a>请参阅  
 [管理发送端口和发送端口组](../core/managing-send-ports-and-send-port-groups.md)