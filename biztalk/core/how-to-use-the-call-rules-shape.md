---
title: "如何使用该调用规则形状 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Call Rules shape [Orchestration Designer], how to
- Call Rules shape [Orchestration Designer], configuring
- Call Rules shape [Orchestration Designer], policies
- policies, Call Rules shape [Orchestration Designer]
ms.assetid: e4bc8a2c-de7e-4e3a-81b8-12bcebb17d27
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a634c2e0a97e627925390610bf4c3039c8afc85c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-call-rules-shape"></a>如何使用调用规则形状
在业务流程设计器中，你可以使用**调用规则**形状以调用业务策略。  
  
### <a name="to-configure-the-call-rules-shape"></a>配置调用规则形状  
  
1.  从工具箱中**BizTalk 业务流程**选项卡上，拖动**调用规则**到业务流程设计图面上的连接线的形状。  
  
     -或者-  
  
     右键单击连接的线条或形状占位符想要添加该形状，指向**插入形状**上下文菜单，然后单击**调用规则**。  
  
    > [!NOTE]
    >  在[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]，不需要具有原子作用域插入**调用规则**形状。 您可以拖动**调用规则**从工具箱调整到业务流程设计图面。 但是，在[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]、**调用规则**菜单项被禁用的上下文菜单中，如果你尝试插入**调用规则**内没有原子作用域的业务流程的形状。 这是与限制[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]产品。  
  
2.  在业务流程设计器中，选择**调用规则**形状。  
  
3.  双击要显示的形状**规则策略配置**对话框。  
  
4.  在**选择你想要调用的业务策略**下拉列表中，选择您需要的策略。  
  
    > [!NOTE]
    >  调用规则配置在确定策略中使用的类型时将查看保存策略的最新版本。 运行时，将使用部署的该策略的最新版本。  
  
5.  在**指定策略参数**列表框中，选择中的某个变量**参数名称**属性。  
  
    > [!NOTE]
    >  **调用规则**形状实质上重新构造消息，就像使用**构造**形状，这又可能导致丢失消息的上下文属性。  
  
    > [!NOTE]
    >  作为参数传递给 BRE 策略，可以指定某个消息或.NET 变量。 若要将传递**TypedXmlDocument**事实，指定相应的消息作为参数业务流程中声明。 若要传递 .NET 事实，请将在业务流程中声明的 .NET 变量指定为参数。 若要将传递数据库事实，指定类型的.NET 变量**该组**或**TypedDataTable**作为参数传递给策略。