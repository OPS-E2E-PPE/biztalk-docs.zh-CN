---
title: 如何使用调用规则形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Call Rules shape [Orchestration Designer], how to
- Call Rules shape [Orchestration Designer], configuring
- Call Rules shape [Orchestration Designer], policies
- policies, Call Rules shape [Orchestration Designer]
ms.assetid: e4bc8a2c-de7e-4e3a-81b8-12bcebb17d27
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9cf784eba26f93e6634863d02d36a4bb2e01c38
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333260"
---
# <a name="how-to-use-the-call-rules-shape"></a>如何使用调用规则形状
在业务流程设计器中，你可以使用**调用规则**形状调用业务策略。  
  
### <a name="to-configure-the-call-rules-shape"></a>若要配置调用规则形状  
  
1. 从工具箱中**BizTalk 业务流程**选项卡上，拖动**调用规则**形状在业务流程设计图面上的连接线上。  
  
    -或-  
  
    右键单击连接的线条或形状占位符，你想要添加形状，指向**插入形状**上下文菜单，然后单击**调用规则**。  
  
   > [!NOTE]
   >  在 BizTalk Server 中，不需要具有原子作用域插入**调用规则**形状。 可以拖动**调用规则**到业务流程设计图面上形状从工具箱。 但是，在 BizTalk Server 中，**调用规则**上下文菜单中禁用菜单项，如果尝试插入**调用规则**不具有原子作用域的业务流程内部的形状。 这是一个限制[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]产品。  
  
2. 在业务流程设计器中，选择**调用规则**形状。  
  
3. 双击该形状以显示**CallRules 策略配置**对话框。  
  
4. 在中**选择你想要调用的业务策略**下拉列表中，选择所需的策略。  
  
   > [!NOTE]
   >  确定策略中使用的类型时，调用规则配置着眼于最新的已保存策略版本。 在运行时，将使用最新的部署的策略版本。  
  
5. 在中**指定策略参数**列表框中，选择从变量**参数名称**属性。  
  
   > [!NOTE]
   >  **调用规则**形状实质上重新构造消息，如同使用**构造**形状，因而可能导致消息丢失的上下文属性。  
  
   > [!NOTE]
   >  您可以指定一条消息或.NET 变量作为 BRE 策略的参数。 要传递**TypedXmlDocument**这一事实，指定作为参数在业务流程中声明的相应消息。 若要传递.NET 事实，指定作为参数的业务流程中声明的.NET 变量。 若要传递数据库事实，指定类型的.NET 变量**DataConnection**或**TypedDataTable**作为策略的参数。