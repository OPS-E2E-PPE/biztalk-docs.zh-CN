---
title: 如何维护词汇版本 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, vocabularies
- vocabularies, creating
- vocabularies, versioning
- vocabularies, publishing
- versioning, vocabularies
- updating, vocabularies
- vocabularies, updating
ms.assetid: 43593c6f-4590-4940-ac17-4015928e5838
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b3c67d79878c59e3b0dcba6dcd15955f34ad97c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254365"
---
# <a name="how-to-maintain-vocabulary-versions"></a>如何维护词汇版本
在向某个版本的词汇中添加了词汇定义之后，可以将该版本保存到规则存储中以用于以后的开发，也可以发布该版本以创建明确定义的不可变数据绑定术语集，用户在开发策略时，可以向规则中添加这些数据绑定术语。 请注意，现有规则将仍指向旧版本。  
  
 本主题包含以下任务的过程：  
  
-   若要保存词汇版本  
  
-   要发布的词汇版本  
  
-   若要创建词汇的更新的版本  
  
-   若要创建空的新版本的词汇  
  
### <a name="to-save-a-vocabulary-version"></a>若要保存词汇版本  
  
-   右键单击版本，并依次**保存**。  
  
### <a name="to-publish-a-vocabulary-version"></a>要发布的词汇版本  
  
-   右键单击版本，并依次**发布**。  
  
### <a name="to-create-an-updated-version-of-a-vocabulary"></a>若要创建词汇的更新的版本  
  
1.  右键单击现有版本，并依次**复制**。  
  
2.  右键单击词汇文件夹中，并依次**粘贴**。  
  
     使用与复制的版本相同的元素，创建新的版本。  
  
### <a name="to-create-an-empty-new-version-of-a-vocabulary"></a>若要创建空的新版本的词汇  
  
-   右键单击词汇文件夹中，并依次**添加新版本**。  
  
    > [!NOTE]
    >  只能使用已发布的词汇中的词汇定义。