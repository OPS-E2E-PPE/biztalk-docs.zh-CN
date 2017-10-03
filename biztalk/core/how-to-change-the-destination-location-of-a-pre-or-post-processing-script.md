---
title: "如何更改预或后续处理脚本的目标位置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- scripts, file locations
- scripts, modifying
- managing [scripts], modifying
- managing [scripts], file locations
ms.assetid: 4a4fdaef-099f-4c29-9815-12404c7a2212
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7eb4ba338790e301e54a9bf262a49808a0a55315
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-change-the-destination-location-of-a-pre--or-post-processing-script"></a>如何更改预或后续处理脚本的目标位置
本主题介绍如何使用 BizTalk Server 管理控制台来更改预或后续处理脚本的目标位置。 这是该脚本复制到其中安装应用程序时的位置。 你可能想要部署到不同环境的应用程序时更改的目标位置。  
  
> [!IMPORTANT]
>  请务必提供卸载应用程序将运行的脚本的目标位置。 如果不这样做，该脚本将不会复制到本地文件系统中，并因此将不会运行卸载过程。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-modify-the-deployment-properties-of-a-pre--or-post-processing-script"></a>若要修改预或后续处理脚本的部署属性  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开包含要修改的脚本的 BizTalk 组，接着展开包含该脚本的应用程序。  
  
3.  单击**资源**文件夹，右键单击该脚本，然后单击**修改**。  
  
4.  在**目标位置**，键入目标位置，包括文件名称的完整路径，然后单击**确定**。 （你可以使用环境变量 %btad_installdir%在路径中指定的应用程序安装文件夹。）  
  
## <a name="see-also"></a>另请参阅  
 [管理前期和后期处理脚本](../core/managing-pre-and-post-processing-scripts.md)