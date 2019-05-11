---
title: 如何更改应用程序的名称 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- naming conventions, renaming
- naming conventions, applications
- applications, renaming
ms.assetid: ae59c792-44bd-43e0-a4ae-e67bcad2e128
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0937e286e0416fbc4d56d155428872144034febc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342449"
---
# <a name="how-to-change-the-name-of-an-application"></a>如何更改应用程序的名称
本主题介绍如何使用 BizTalk Server 管理控制台来更改应用程序的名称。 您使用的应用程序名称不能已存在的组中。  
  
> [!NOTE]
>  如果你已导出具有已重命名应用程序的引用的应用程序的.msi 文件，该引用将不再起作用时导入.msi 文件。 你将需要使用新的应用程序名称更新该引用。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-change-the-name-of-an-application"></a>若要更改应用程序的名称  
  
1. 单击**启动**，依次指向**程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开**BizTalk Server 管理**，右键单击你想要更改，然后单击其名称的应用程序**属性**。  
  
3. 在中**名称**框中，键入该应用程序的新名称，然后单击**确定**。  
  
## <a name="see-also"></a>请参阅  
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)