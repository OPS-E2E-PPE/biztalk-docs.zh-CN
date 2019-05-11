---
title: 如何测试策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, policies
- Business Rule Composer, testing
- Business Rule Composer, policies
- testing, Business Rule Composer
- policies, testing
ms.assetid: 122dee26-d1f1-49a6-a6d5-a9d3d861a66b
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49c682645a534f43476244fcda26453944048168
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383727"
---
# <a name="how-to-test-policies"></a>如何测试策略
若要测试策略，需要可对其执行规则的事实。 可以通过在 XML 文档中指定值添加事实或数据库表，将指向策略测试器，或者您可以使用事实创建器向引擎提供.NET 对象作为事实的数组。 有关详细信息，请参阅[创建事实创建器](../core/how-to-create-a-fact-creator.md)。  
  
### <a name="to-test-a-policy-in-the-business-rule-composer"></a>若要在业务规则编辑器测试策略  
  
1.  在策略浏览器窗口中，单击你想要测试的策略版本。  
  
2.  单击**测试策略**菜单栏上的按钮 （绿色箭头）。  
  
     顶部窗格显示策略规则引用的事实类型。  
  
3.  若要添加事实实例，请单击**XML 文档**或**数据库表**事实类型，然后再单击**添加实例**。  
  
4.  如果你想要删除事实实例，请单击相应的事实类型，然后单击**删除实例**。  
  
5.  如果你想要添加已编写事实创建器，请单击**添加**事实创建器窗格中。  
  
6.  单击**测试**。  
  
     策略测试跟踪输出将显示在测试输出窗口中。  
  
7.  用鼠标右键单击输出窗口来保存、 清除、 选择，或复制输出文本。  
  
     ![](../core/media/ebiz-testpolicy.gif "ebiz_testpolicy")  
选择事实以测试策略