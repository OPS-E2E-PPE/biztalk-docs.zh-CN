---
title: 如何开发词汇 |Microsoft 文档
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
ms.openlocfilehash: 2644cc938cbe5e42f4e124453d863741755d965d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249053"
---
# <a name="how-to-develop-vocabularies"></a>如何开发词汇
规则条件和操作基于源可能有详细说明，告知用户只需少量或者无有关它们的指的困难读取绑定信息。 业务规则框架，可创建用于通过提供直观、 特定于域的用户可以将与规则条件和操作相关联的术语的用户简化的规则的开发的词汇。  
  
 你可以标识数据源以使用，创建新的词汇，并向它添加词汇定义。 你可以将你词汇的版本保存到规则存储，并完成时，可以将其用户提供明确定义的、 不可变的一组绑定到数据引用的条款发布。  
  
 如果你需要在将来对你词汇进行更改，你可以只需创建反映所做的更改的词汇的新版本。  
  
> [!CAUTION]
>  创建新版本的词汇后，从早期版本生成的规则仍将指向以前的版本。  
  
### <a name="to-create-a-vocabulary"></a>若要创建的词汇  
  
1.  在事实浏览器窗口中，单击**词汇**选项卡。  
  
2.  右键单击**词汇**文件夹，，然后单击**添加新词汇**。  
  
     一个新**词汇**文件夹显示在**词汇**文件夹。  
  
3.  单击新建**词汇**文件夹，然后再编辑属性窗口中的名称。  
  
    > [!NOTE]
    >  你可以重命名词汇之前或策略，必须保存所有内容 （所有版本的工作定义）。