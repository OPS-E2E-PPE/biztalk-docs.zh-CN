---
title: 如何更改预处理或后处理脚本的目标位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- scripts, file locations
- scripts, modifying
- managing [scripts], modifying
- managing [scripts], file locations
ms.assetid: 4a4fdaef-099f-4c29-9815-12404c7a2212
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f6d1a7ec9f661a86ff028b1ec364bbd656cbb2b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005286"
---
# <a name="how-to-change-the-destination-location-of-a-pre--or-post-processing-script"></a>如何更改预处理或后处理脚本的目标位置
本主题介绍如何使用 BizTalk Server 管理控制台来更改预处理或后处理脚本的目标位置。 这是该脚本复制到其中安装应用程序的位置。 您可能想要部署到不同环境的应用程序时更改的目标位置。  
  
> [!IMPORTANT]
>  请务必提供卸载应用程序时将运行的脚本的目标位置。 如果不这样做，脚本将不会复制到本地文件系统中，并因此将不在卸载期间运行。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-modify-the-deployment-properties-of-a-pre--or-post-processing-script"></a>若要修改预处理或后处理脚本的部署属性  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开 [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后展开包含要修改的脚本的 BizTalk 组，接着展开包含该脚本的应用程序。  
  
3. 单击**资源**文件夹中，右键单击脚本，然后依次**修改**。  
  
4. 在中**目标位置**，键入目标位置，包括文件名称的完整路径，然后单击**确定**。 （您可以使用环境变量 %btad_installdir%在路径中指定应用程序安装文件夹。）  
  
## <a name="see-also"></a>请参阅  
 [管理预处理脚本和后期处理脚本](../core/managing-pre-and-post-processing-scripts.md)