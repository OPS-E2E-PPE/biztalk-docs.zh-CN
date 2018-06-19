---
title: 如何更改应用程序的名称 |Microsoft 文档
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
ms.openlocfilehash: 4826688935bf18cd5288924d4544f484b3dcf0cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248189"
---
# <a name="how-to-change-the-name-of-an-application"></a>如何更改应用程序的名称
本主题介绍如何使用 BizTalk Server 管理控制台更改应用程序的名称。 您使用的应用程序名称不能已存在于该组中。  
  
> [!NOTE]
>  如果您为具有对重命名应用程序的引用的应用程序导出某一 .msi 文件，则在您导入该 .msi 文件时，该引用将不再有效。 您将需要使用新的应用程序名称更新该引用。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-change-the-name-of-an-application"></a>更改应用程序的名称  
  
1.  单击**启动**，指向**程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**，右键单击你想要更改，然后单击其名称的应用**属性**。  
  
3.  在**名称**框中，键入应用程序的新名称，然后单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [创建和修改 BizTalk 应用程序](../core/creating-and-modifying-biztalk-applications.md)