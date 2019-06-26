---
title: 如何将发送端口添加到发送端口组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [send port groups], adding send ports
- managing [send ports], adding to send port groups
- send port groups, send ports
- send ports, send port groups
- adding, send ports
ms.assetid: a61b3b32-c05e-40b9-abf1-09b7065fb6a2
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac058035c088e0be28f742109abfd8dae6e81552
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65343344"
---
# <a name="how-to-add-a-send-port-to-a-send-port-group"></a>如何将发送端口添加到发送端口组
本主题介绍如何使用 BizTalk Server 管理控制台来添加一个或多个发送端口与发送端口组。 只能向发送端口组添加单向静态发送端口。  
  
 可以在不同的应用程序中添加存在的发送端口。 如果这样做，您必须从包含到包含发送端口的应用程序中的发送端口组的应用程序添加的引用。 有关说明，请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-add-a-send-port-to-a-send-port-group"></a>若要向发送端口组添加发送端口  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开 BizTalk 组和 BizTalk 应用程序想要向发送端口组添加发送端口。  
  
3. 单击**发送端口组**，右键单击发送端口组，并单击**属性**。  
  
4. 在**发送端口**，单击下拉列表下的**名称**，然后单击要添加到发送端口组的发送端口。 为你想要添加到组的每个发送端口重复。 若要创建新的发送端口并将其添加，请单击 **\<新发送端口...\>**  ，然后按照中的说明[如何创建发送端口](../core/how-to-create-a-send-port2.md)。  
  
5. 完成向发送端口组添加发送端口，请单击**确定**。  
  
## <a name="see-also"></a>请参阅  
 [创建和配置发送端口组](../core/creating-and-configuring-send-port-groups.md)   
 [创建和配置发送端口](../core/creating-and-configuring-send-ports.md)