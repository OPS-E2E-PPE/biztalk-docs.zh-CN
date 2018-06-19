---
title: 配置信息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Call Rules shape [Orchestration Designer], planning
- Call Rules shape [Orchestration Designer], configuring
ms.assetid: aa4924c6-4270-473b-aa0a-6d8b18375a39
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9a35767815eaf7406a7baae5d9dccb833492287
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233461"
---
# <a name="configuration-information"></a>配置信息
本主题介绍如何配置**调用规则**形状。  
  
## <a name="orchestration-variables-and-fact-types"></a>业务流程变量和事实类型  
 业务流程中其中**调用规则**形状驻留中，你必须具有与策略中使用的类型匹配的变量。 如果没有正确的变量类型，则无法向策略提供正确的参数。 假设你拥有**调用规则**形状中业务流程、 CallMyRules，和你使用 CallMyRules 调用 MyPolicy。 如果在 MyPolicy 中使用了 .NET 类 MyClass，则必须在业务流程中创建 MyAssembly.MyClass 类型的变量。 同样，如果 MyPolicy 具有**该组**绑定，你必须创建的变量**Microsoft.RuleEngine.DataConnection**业务流程中的类型。  
  
 除了在业务流程中创建此类变量以外，您还必须为这些变量创建实例。 你可以执行此操作通过添加**表达式**形状上与您的业务流程。 使用前面的示例中，你应实例化 MyAssembly.MyClass 实例和一个**该组**实例。 若要实例化**该组**实例，你执行以下操作：  
  
-   创建**SqlConnection**实例，并将其分配给 MySqlCon。  
  
-   创建**该组**实例，并将其分配给该组 (变量来**该组**类型)，如下面的代码段中所示：  
  
    ```  
    dataConnection = new Microsoft.RuleEngine.DataConnection("NameOfSqlDatabaseHere", "NameOfYourTableHere", MySqlCon);  
    ```  
  
> [!NOTE]
>  如果没有匹配的事实类型的变量，这些类型将不会显示为中的参数**指定策略参数**列表框中的**规则策略配置**对话框。  
  
> [!NOTE]
>  业务流程引擎会自动将转换为 BRE 策略到参数指定的消息变量**TypedXmlDocument**对象，并断言它们到工作之前执行策略的规则引擎的内存。 因此，不需要像对 .NET 和数据库事实那样，声明 TypedXmlDocument 类型的变量。  
  
## <a name="message-type-and-document-type"></a>消息类型和文档类型  
 你必须确保**DocumentType**使用你的业务规则 （即你在业务规则编辑器中实现） 的 XML 节点的属性等同于**MessageType**中定义这些 XML 节点业务流程-它必须匹配**MessageType**消息或将传递给规则引擎中的消息部分的**调用规则**形状。  
  
 例如，如果在 BizTalk 项目中，定义采购订单 (PO) XML 架构**MessageType**为此架构定义**BTSProject.PO** (如果**BTSProject**是命名空间或使用默认命名空间的项目名称）。  
  
 情况下**PO\Amount**元素，则将其删除为规则的定义之前, 必须更改其**DocumentType**属性**BTSProject.PO**在属性窗口. 架构中的任何节点上选择后，你可以访问属性窗口**XML 架构**事实数据资源管理器中的选项卡。 所做的更改将应用于架构中的所有元素，但不会随架构一起保存。 启动业务规则编辑器或重新加载架构后，必须重新进行设置。 对于基于 XML 架构或基于直接从 XML 架构生成的规则的词汇定义来说，这是必需的操作。 如果不这样做，你仍可以执行策略，但**调用规则**形状将无法正常运行，和消息类型不会出现在**指定策略参数**列表框中的**规则策略配置**对话框。