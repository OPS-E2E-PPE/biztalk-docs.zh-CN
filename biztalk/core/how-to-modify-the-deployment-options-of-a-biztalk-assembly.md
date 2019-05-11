---
title: 如何修改 BizTalk 程序集的部署选项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- modifying, deploying
- managing [assemblies], modifying
- deploying, assemblies
- managing [assemblies], deploying
- assemblies, deploying
ms.assetid: d25e2f71-08bd-4786-ab6c-35ae4e88b8cc
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2cf808f35d4ce33a2ea821f2bb07bf1b98d0a76d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384556"
---
# <a name="how-to-modify-the-deployment-options-of-a-biztalk-assembly"></a>如何修改 BizTalk 程序集的部署选项
本主题介绍如何使用 BizTalk Server 管理控制台修改 BizTalk 程序集的部署选项。  
  
 可以指定以下部署选项：  
  
-   **将添加到全局程序集缓存添加资源 (gacutil)。** 如果选择此选项，该程序集时将添加到全局程序集缓存 (GAC) 在本地计算机上该程序集添加到应用程序。 此外，如果您以后刷新该程序集 (右键单击它，然后单击**刷新**)，该程序集添加到 GAC。 清除此选项的复选框不会删除该程序集从 GAC 中，如果当前存在。  
  
-   **将添加到 MSI 文件导入 (gacutil) 上的全局程序集缓存。** 导入应用程序.msi 文件时，将程序集安装到本地计算机上的 GAC。  
  
-   **添加到全局程序集缓存 (gacutil) 安装 MSI 文件。** 从.msi 文件安装应用程序时，将程序集安装到本地计算机上的 GAC。  
  
-   **目标位置：** 在安装应用程序的程序集文件将复制到的路径。 如果未提供路径，程序集文件不会复制到本地文件系统上安装。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 此外，如果您选择立即将程序集添加到 GAC 的选项，你的帐户还必须是本地管理员组的成员。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-modify-the-deployment-options-of-a-biztalk-assembly"></a>若要修改的 BizTalk 程序集的部署选项  
  
1. 单击**启动**，单击**程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，依次展开 BizTalk Server 管理、 包含要修改其部署选项的 BizTalk 程序集的 BizTalk 组和包含 BizTalk 程序集的应用程序。  
  
3. 单击**资源**文件夹中，右键单击 BizTalk 程序集，然后依次**修改**。  
  
4. 在中**选项**，选中所需的部署选项的复选框。  
  
5. 如果需要，在**目标位置**编辑的路径，该程序集将安装该应用程序时，复制，然后单击**确定**。  
  
## <a name="see-also"></a>请参阅  
 [管理 BizTalk 程序集](../core/managing-biztalk-assemblies.md)