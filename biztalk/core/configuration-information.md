---
title: 配置信息 |Microsoft Docs
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
ms.openlocfilehash: a9d58c810f4c0a01046d900f8654556f523f7a27
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356488"
---
# <a name="configuration-information"></a>配置信息
本主题介绍如何配置**调用规则**形状。  
  
## <a name="orchestration-variables-and-fact-types"></a>业务流程变量和事实类型  
 在业务流程中位置**调用规则**驻留形状中，你必须具有匹配策略中使用的类型的变量。 如果没有正确的变量类型，不能提供该策略的正确参数。 假设您有**调用规则**形状在业务流程、 CallMyRules，并且您使用 CallMyRules 调用 MyPolicy。 如果在 MyPolicy 中使用.NET 类 MyClass，则必须在业务流程中创建 MyAssembly.MyClass 类型的变量。 同样，如果具有**DataConnection**绑定，必须创建的变量**Microsoft.RuleEngine.DataConnection**业务流程中的类型。  
  
 除了在业务流程中创建此类变量，还必须创建这些变量的实例。 您可以执行此操作通过添加**表达式**向业务流程的形状。 使用前面的示例中，您应实例化 MyAssembly.MyClass 实例和一个**DataConnection**实例。 若要实例化**DataConnection**实例，则执行以下操作：  
  
-   创建**SqlConnection**实例，并将其分配给 MySqlCon。  
  
-   创建**DataConnection**实例，并将其分配给 dataConnection (变量**DataConnection**类型)，如以下代码片段中所示：  
  
    ```  
    dataConnection = new Microsoft.RuleEngine.DataConnection("NameOfSqlDatabaseHere", "NameOfYourTableHere", MySqlCon);  
    ```  
  
> [!NOTE]
>  如果没有匹配的事实类型的变量，这些类型将不会显示作为中的参数**指定策略参数**列表框中的**CallRules 策略配置**对话框。  
  
> [!NOTE]
>  业务流程引擎会自动将转换为到 BRE 策略的参数指定的消息变量**TypedXmlDocument**对象，并将它们添加到工作内存中的规则引擎在执行该策略之前。 因此，不需要声明 TypedXmlDocument 类型的变量，如你对.NET 和数据库事实。  
  
## <a name="message-type-and-document-type"></a>消息类型和文档类型  
 您必须确保**DocumentType** （即在业务规则编辑器中实现时） 在业务规则中使用的 XML 节点的属性是与相同**MessageType**中定义的 XML 节点业务流程，则它必须匹配**MessageType**的消息或将其传递到规则引擎的消息部分**调用规则**形状。  
  
 例如，如果在 BizTalk 项目中，定义采购订单 (PO) XML 架构**MessageType**为此架构定义**BTSProject.PO** (如果**BTSProject**是命名空间或使用默认命名空间的项目名称）。  
  
 情况下**PO\Amount**元素，才能删除为规则的定义，则必须更改其**DocumentType**属性设置为**BTSProject.PO**属性窗口中. 在选择架构中的任何节点后，可以访问属性窗口**XML 架构**在事实浏览器选项卡。 此更改将应用于的所有元素在架构中，但不是保留与架构。 业务规则编辑器启动或重新加载架构时，它必须重置。 这是必需的基于 XML 架构或直接从 XML 架构生成的规则的词汇定义。 如果不这样做，则仍可以执行策略，但**调用规则**形状将无法正常工作，并且消息类型将出现在**指定策略参数**列表框中的**CallRules 策略配置**对话框。