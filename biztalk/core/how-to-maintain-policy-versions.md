---
title: 如何维护策略版本 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- policies, publishing
- publishing policies
- updating, policies
- versioning, policies
- policies, versioning
- policies, updating
ms.assetid: 6e35b2bd-1ecd-45ea-aff3-4ad2437568a4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78750e9db681ad12b1a134ef27360a57a3163bc1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65336831"
---
# <a name="how-to-maintain-policy-versions"></a>如何维护策略版本
将规则添加到你的策略的版本后，可以将该版本保存到规则存储中供进一步开发，也可以发布它以创建明确定义的、 不可变的一组可部署在基于规则的应用程序中使用的规则。  
  
 本主题包含以下任务的过程：  
  
-   若要创建新的空策略版本  
  
-   若要保存策略版本  
  
-   若要发布策略版本  
  
-   若要创建策略的更新的版本  
  
-   更新策略以使用更新的程序集  
  
### <a name="to-create-an-empty-new-version-of-a-policy"></a>若要创建新的空策略版本  
  
-   右键单击策略文件夹，然后依次**添加新版本**。  
  
### <a name="to-save-a-policy-version"></a>若要保存策略版本  
  
-   右键单击策略版本中，然后依次**保存**。  
  
### <a name="to-publish-a-policy-version"></a>若要发布策略版本  
  
-   右键单击策略版本中，然后依次**发布**。  
  
### <a name="to-create-an-updated-version-of-a-policy"></a>若要创建策略的更新的版本  
  
1.  右键单击现有的策略版本，然后依次**复制**。  
  
2.  右键单击策略文件夹，然后依次**粘贴**。  
  
     创建一个新版本，具有与复制的版本相同的元素。  
  
    > [!NOTE]
    >  如果您的策略使用.NET 程序集，并且更新的程序集，应将策略绑定到程序集的较新版本。  
  
### <a name="to-update-a-policy-to-use-an-updated-assembly"></a>更新策略以使用更新的程序集  
  
1.  单击**启动**，依次指向**管理工具**，指向 **.NET Framework 配置**，然后单击**配置程序集**.  
  
2.  转到属性目标程序集并单击**绑定策略**选项卡。  
  
3.  在全局程序集缓存中，更改到较新版本的版本号。  
  
    > [!NOTE]
    >  使用策略的所有程序集应添加到全局程序集缓存中。