---
title: "如何创建发送端口组 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- creating, send port groups
- send port groups, creating
- managing [send port groups], creating
ms.assetid: de3e72aa-83f4-4760-9f39-a488f904f1d3
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f308c950d56569c06403df1394580302089a453e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-a-send-port-group"></a>如何创建发送端口组
本主题介绍如何使用 BizTalk Server 管理控制台在 BizTalk 应用程序中创建发送端口组，然后向其中添加发送端口。 仅向发送端口组，可以添加静态单向发送端口。 若要路由消息，发送端口组必须至少包含一个发送端口。  
  
 可以添加其他应用程序中存在的发送端口。 如果进行这种添加，必须将包含发送端口组的应用程序的引用添加到包含此发送端口的应用程序。 有关说明，请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，则必须以 BizTalk Server Administrators 组成员的身份登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-create-a-send-port-group"></a>创建发送端口组  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开要在其中创建发送端口组的 BizTalk 组和 BizTalk 应用程序。  
  
3.  右键单击**发送端口组**，指向**新建**，然后单击**发送端口组**。  
  
4.  在**名称**框中，键入发送端口组的名称。  
  
5.  在**发送端口**，单击下的下拉列表**名称**，然后单击发送端口将添加到发送端口组。 对每个要添加到该组的发送端口重复此步骤。 若要创建新的发送端口并将其添加，请单击**\<新建发送端口..>** ，然后按照中的说明[如何创建发送端口](../core/how-to-create-a-send-port2.md)。  
  
6.  完成后将发送端口添加到发送端口组，单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [创建和配置发送端口组](../core/creating-and-configuring-send-port-groups.md)