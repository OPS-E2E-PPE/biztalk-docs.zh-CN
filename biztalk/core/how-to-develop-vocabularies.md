---
title: 如何制定词汇 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, vocabularies
- vocabularies, business rules
- business rules, vocabularies
- vocabularies, creating
ms.assetid: 5c16eb98-2257-44f2-8a29-899e02f7e556
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1aac6d9350b3f93df3755b3b082db9e8e5ab7f6f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338422"
---
# <a name="how-to-develop-vocabularies"></a>如何制定词汇
规则条件和操作基于源可能具有详细说明，告知用户很少或 nothing 有关它们的指很难读取绑定信息。 业务规则框架，可创建词汇，以便通过向用户提供直观的、 特定于域的用户可以将与规则条件和操作相关联的术语来简化开发的规则。  
  
 您可以确定数据源使用，创建新的词汇，并向其添加词汇定义。 可以将词汇的版本保存到规则存储中，并完成后，你可以发布它，向用户提供定义完善且不可变的一组绑定到的数据引用的条款。  
  
 如果需要在将来对词汇进行更改，可以简单地创建反映所做的更改的词汇的新版本。  
  
> [!CAUTION]
>  创建新的词汇版本后，从以前的版本生成的规则将仍指向以前的版本。  
  
### <a name="to-create-a-vocabulary"></a>若要创建词汇  
  
1.  在事实浏览器窗口中，单击**词汇**选项卡。  
  
2.  右键单击**词汇**文件夹，，然后单击**添加新词汇**。  
  
     一个新**词汇**文件夹下显示**词汇**文件夹。  
  
3.  单击新建**词汇**文件夹，然后再编辑属性窗口中的名称。  
  
    > [!NOTE]
    >  您可以重命名某一词汇或策略，必须保存全部内容 （所有版本的定义）。