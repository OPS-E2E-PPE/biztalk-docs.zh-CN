---
title: 如何添加接收位置接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- receive locations, adding to receive ports
- managing [receive ports], adding receive locations
- receive ports, adding receive locations
- adding, receive locations
ms.assetid: a71d50dc-629e-4b7f-aa59-6d2274d4cac3
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a2749a6593d116695c2af214e2d817478c24e44
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387260"
---
# <a name="how-to-add-a-receive-location-to-a-receive-port"></a>如何添加接收位置接收端口
本主题介绍如何使用 BizTalk Server 管理控制台将新的接收位置添加到接收端口。  
  
> [!NOTE]
>  您可以将绑定接收端口到业务流程时配置应用程序，如中所述[如何配置应用程序](../core/how-to-configure-an-application.md)或当您将业务流程绑定，如中所述[如何配置绑定业务流程](../core/how-to-configure-bindings-for-an-orchestration.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-add-a-receive-location-to-a-receive-port"></a>若要添加到接收端口的接收位置  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开 BizTalk 组和 BizTalk 应用程序想要添加到接收端口的接收位置。  
  
3. 单击**接收端口**，右键单击你想要添加接收位置，指向的接收端口**新建**，然后单击**接收位置**。  
  
4. 在中**名称**，键入新的接收位置的名称。  
  
5. 按照中的说明配置接收位置属性[如何创建接收位置](../core/how-to-create-a-receive-location.md)，然后单击**确定**。  
  
## <a name="see-also"></a>请参阅  
 [管理接收端口](../core/managing-receive-ports.md)