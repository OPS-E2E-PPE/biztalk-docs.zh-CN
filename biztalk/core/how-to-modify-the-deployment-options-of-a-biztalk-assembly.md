---
title: "如何修改 BizTalk 程序集的部署选项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- modifying, deploying
- managing [assemblies], modifying
- deploying, assemblies
- managing [assemblies], deploying
- assemblies, deploying
ms.assetid: d25e2f71-08bd-4786-ab6c-35ae4e88b8cc
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 416fc38c8768e7391659d133877b2ae59e704463
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-modify-the-deployment-options-of-a-biztalk-assembly"></a>如何修改 BizTalk 程序集的部署选项
本主题介绍如何使用 BizTalk Server 管理控制台修改 BizTalk 程序集的部署选项。  
  
 您可以指定以下部署选项：  
  
-   **将添加到全局程序集缓存在添加资源 (gacutil)。** 如果选择此选项，则在将程序集添加到应用程序时，该程序集将添加到本地计算机上的全局程序集缓存 (GAC) 中。 此外，如果你更高版本刷新程序集 (右键单击它，然后单击**刷新**)，此程序集添加到 GAC。 清除此选项的复选框并不从 GAC 删除该程序集（如果该程序集当前在 GAC 中存在）。  
  
-   **将添加到 MSI 文件导入 (gacutil) 上的全局程序集缓存。** 导入应用程序 .msi 文件时将程序集安装到本地计算机的 GAC 中。  
  
-   **将添加到 MSI 文件安装 (gacutil) 上的全局程序集缓存。** 从 .msi 文件安装应用程序时将程序集安装到本地计算机的 GAC 中。  
  
-   **目标位置：**时安装的应用程序，则将复制到此程序集文件的路径。 如果不提供此路径，则在安装过程中，该程序集文件将不会被复制到本地文件系统。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 此外，如果您选择立即将程序集添加到 GAC 中的选项，则您的帐户必须也是本地管理员组的成员。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-modify-the-deployment-options-of-a-biztalk-assembly"></a>修改 BizTalk 程序集的部署选项  
  
1.  单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，依次展开“[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] 管理”、包含要修改其部署选项的 BizTalk 程序集的 BizTalk 组，以及包含该 BizTalk 程序集的应用程序。  
  
3.  单击**资源**文件夹中，右键单击 BizTalk 程序集，并依次**修改**。  
  
4.  在**选项**，选中所需的部署选项的复选框。  
  
5.  如有必要，在**目标位置**编辑的路径，其中程序集将安装应用程序时，复制，然后单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [管理 BizTalk 程序集](../core/managing-biztalk-assemblies.md)