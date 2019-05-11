---
title: 如何删除接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive locations], deleting
- receive locations, deleting
- deleting, receive locations
ms.assetid: aa859355-af4c-48d9-b224-78fd3ef618fc
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fadf61b4791234076ae7e77be0ec6447a4aeda7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385361"
---
# <a name="how-to-delete-a-receive-location"></a>如何删除接收位置
本主题介绍如何使用 BizTalk Server 管理控制台来删除接收位置。 删除接收位置时，它从 BizTalk 管理数据库中删除，并且不再显示在 BizTalk Server 管理控制台。  
  
 在删除接收位置时，请记住以下重要事项：  
  
-   删除接收位置之前，它必须先将其禁用，如中所述[如何禁用接收位置](../core/how-to-disable-a-receive-location.md)。  
  
-   无法删除接收端口的主接收位置。 如果尝试这样做，您将收到一条错误消息。 若要删除接收位置，您可以删除接收端口，这还会删除所有包含，也可以将其他接收位置设为主，然后删除原来的接收位置的接收位置。 有关将接收位置设为主接收位置的说明，请参阅[如何编辑接收位置属性](../core/how-to-edit-the-properties-of-a-receive-location.md)。  
  
-   删除接收位置后，重新启动独立主机工作进程对应于已删除的接收位置。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-delete-a-receive-location"></a>若要删除接收位置  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开 BizTalk 组和 BizTalk 应用程序想要删除接收位置。  
  
3. 单击**接收位置**，右键单击要删除，然后单击该接收位置**删除**。  
  
## <a name="see-also"></a>请参阅  
 [管理接收位置](../core/managing-receive-locations.md)