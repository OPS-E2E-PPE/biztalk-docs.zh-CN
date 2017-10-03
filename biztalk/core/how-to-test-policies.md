---
title: "如何测试策略 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing, policies
- Business Rule Composer, testing
- Business Rule Composer, policies
- testing, Business Rule Composer
- policies, testing
ms.assetid: 122dee26-d1f1-49a6-a6d5-a9d3d861a66b
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f7a0f8c0d63d14d5a529039a6e1c8af5b363cc9c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-test-policies"></a>如何测试策略
若要测试策略，您需要可对其执行规则的事实。 通过在将在策略测试器中指向的 XML 文档或数据库表中指定值，可以添加事实；也可以使用事实创建器向引擎提供 .NET 对象数组作为事实。 有关详细信息，请参阅[创建事实创建者](../core/how-to-create-a-fact-creator.md)。  
  
### <a name="to-test-a-policy-in-the-business-rule-composer"></a>在业务规则编辑器中测试策略  
  
1.  在“策略浏览器”窗口中，单击要测试的策略版本。  
  
2.  单击**测试策略**菜单栏上的按钮 （绿色箭头）。  
  
     顶部窗格将显示策略规则引用的事实类型。  
  
3.  若要添加的事实实例，请单击**XML 文档**或**数据库表**事实键入，然后单击**添加实例**。  
  
4.  如果你想要删除的事实实例，单击相应的事实类型，然后单击**删除实例**。  
  
5.  如果你想要添加你编写了一个事实创建者，请单击**添加**事实创建者窗格中。  
  
6.  单击**测试**。  
  
     策略测试跟踪输出将显示在测试输出窗口中。  
  
7.  右键单击输出窗口可保存、清除、选择或复制输出文本。  
  
     ![](../core/media/ebiz-testpolicy.gif "ebiz_testpolicy")  
选择事实以测试策略