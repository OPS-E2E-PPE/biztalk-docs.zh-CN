---
title: "如何更改默认应用程序 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- applications, default
- applications, modifying
- modifying, applications
ms.assetid: cfa5e88f-0bbb-4edd-a840-722dcdcce266
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33b4ffb6fbbb2463b20a7d344d0f7f27811de23b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-change-the-default-application"></a>如何更改默认应用程序
本主题介绍如何通过在 BizTalk Server 管理控制台中编辑应用程序的属性来更改默认应用程序。 你还可以更改默认应用程序通过创建新的应用程序并指定为默认应用程序中所述[如何创建应用程序](../core/how-to-create-an-application.md)。  
  
 安装 BizTalk Server 时，BizTalk 管理数据库中会创建一个名为“BizTalk 应用程序 1”的默认应用程序，并显示在 BizTalk Server 管理控制台中。 将 BizTalk Server 的早期版本升级时，您的项目会被自动放入此应用程序中。 此外，使用 BTSTask 导入 Windows Installer (.msi) 文件时，如果不指定应用程序，则该 .msi 文件中的项目将被导入到默认应用程序中。  
  
 您无法删除默认应用程序，但可以更改哪一个应用程序作为默认应用程序。 更改默认应用程序后，如果需要，可以删除先前的默认应用程序。 有关说明，请参阅[如何从 BizTalk 组中删除 BizTalk 应用程序](../core/how-to-delete-a-biztalk-application-from-the-biztalk-group.md)。  
  
 更改默认应用程序时，所有项目仍保留在原默认应用程序中。 如果需要，您可将这些项目显式移出该应用程序。 有关说明，请参阅[如何将项目移到不同的应用程序](../core/how-to-move-an-artifact-to-a-different-application.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-change-the-default-application"></a>更改默认应用程序  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**、 展开的 BizTalk 组，右键单击你想要进行默认情况下，，然后单击应用程序**属性**。  
  
3.  选择**使这成为默认应用**复选框，然后单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)