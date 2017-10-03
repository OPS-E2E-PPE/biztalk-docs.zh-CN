---
title: "如何维护策略版本 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- policies, publishing
- publishing policies
- updating, policies
- versioning, policies
- policies, versioning
- policies, updating
ms.assetid: 6e35b2bd-1ecd-45ea-aff3-4ad2437568a4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 09c73b3575ec484ab611fccac920cef6d96d3800
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-maintain-policy-versions"></a>如何维护策略版本
向策略版本添加规则后，您可以将该版本保存到规则存储中以供进一步开发使用，或者也可发布该版本以创建定义明确并且不可改变的规则集（可以部署此规则集以便在基于规则的应用程序中使用）。  
  
 本主题包含以下任务的过程：  
  
-   创建新的空策略版本  
  
-   保存策略版本  
  
-   发布策略版本  
  
-   创建策略的更新版本  
  
-   更新策略以使用更新的程序集  
  
### <a name="to-create-an-empty-new-version-of-a-policy"></a>创建新的空策略版本  
  
-   右键单击策略文件夹，然后单击**添加新版本**。  
  
### <a name="to-save-a-policy-version"></a>保存策略版本  
  
-   右键单击策略版本中，并依次**保存**。  
  
### <a name="to-publish-a-policy-version"></a>发布策略版本  
  
-   右键单击策略版本中，并依次**发布**。  
  
### <a name="to-create-an-updated-version-of-a-policy"></a>创建策略的更新版本  
  
1.  右键单击现有策略版本，并依次**复制**。  
  
2.  右键单击策略文件夹，然后单击**粘贴**。  
  
     使用与复制的版本相同的元素，创建新的版本。  
  
    > [!NOTE]
    >  如果您的策略使用一个 .NET 程序集，而该程序集进行了更新，则应将策略绑定到该程序集的更新版本。  
  
### <a name="to-update-a-policy-to-use-an-updated-assembly"></a>更新策略以使用更新的程序集  
  
1.  单击**启动**，指向**管理工具**，指向**.NET Framework 配置**，然后单击**配置程序集**.  
  
2.  转到属性目标的程序集和单击**绑定策略**选项卡。  
  
3.  在全局程序集缓存中，将版本号更改为更新版本的版本号。  
  
    > [!NOTE]
    >  策略使用的所有程序集都应添加到全局程序集缓存中。