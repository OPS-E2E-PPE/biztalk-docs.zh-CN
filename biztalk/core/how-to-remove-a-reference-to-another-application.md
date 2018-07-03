---
title: 如何删除对另一个应用程序的引用 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- applications, references
ms.assetid: cc867706-7c56-4386-b7ec-9fd7cf6c83a4
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f995d16d2ef4d45f734058887469863ecabd624
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970598"
---
# <a name="how-to-remove-a-reference-to-another-application"></a>如何删除对另一应用程序的引用
本主题介绍如何使用 BizTalk Server 管理控制台从一个应用程序删除对另一应用程序的引用。 如果不再需要在当前应用程序中使用在同一 BizTalk 组中的另一应用程序中存在的项目，就要删除引用。 有关添加引用的详细信息，请参阅[如何添加对另一个应用程序的引用](../core/how-to-add-a-reference-to-another-application.md)。  
  
 如果当前应用程序中的项目仍然使用引用应用程序中的项目，删除引用的操作将失败。  
  
> [!CAUTION]
>  BizTalk Server 中的每个应用程序都自动包含对 BizTalk.System 应用程序的引用。 这是因为 BizTalk.System 包含的项目会被每一个 BizTalk 应用程序使用。 绝不能删除对 BizTalk.System 应用程序的引用。 如果删除了，则应用程序无法正常运行。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-remove-a-reference-to-another-application"></a>删除对另一应用程序的引用  
  
1. 单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开**BizTalk Server 管理**，右键单击你想要删除的引用 （引用另一个应用程序的一个），应用的程序，然后单击**属性**.  
  
3. 在属性页的左窗格中，单击**引用**。  
  
4. 在右窗格中，单击你不再想要引用此应用程序中，单击应用程序**删除**，然后单击**确定**。  
  
## <a name="see-also"></a>请参阅  
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)