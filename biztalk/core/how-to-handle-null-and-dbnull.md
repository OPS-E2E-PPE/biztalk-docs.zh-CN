---
title: 如何处理 Null 和 DBNull |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, NULL
ms.assetid: d235c265-4947-470b-9f2d-9936ae1b88a1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b07ac74828a858b368cac5d401081a58b8602323
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-handle-null-and-dbnull"></a>如何处理 Null 和 DBNull
本主题介绍处理与不同类型相关的 null 值时的预期行为，并讨论用于检查特定字段或成员是否为 null（即是否存在）的选项。  
  
## <a name="xml"></a>XML  
 以下准则适用于 XML：  
  
-   XML 值将永远不会作为 null 值从文档返回。 它返回空字符串或“不存在”错误。 如果是空字符串，则转换特定类型（例如，生成规则时将字段指定为整数类型）时可能会发生错误。  
  
-   业务规则编辑器不允许你将字段设置为 null 或设置字段的类型**对象**。  
  
-   通过对象模型中，你可以将类型为**对象**。 在这种情况下，返回的值是 XPath 计算结果的类型- **float**，**布尔**，或**字符串**，取决于 XPath 表达式。  
  
## <a name="net-classes"></a>.NET 类  
 以下情况适用于 .NET 类：  
  
-   不允许为 null 比较，如果返回类型不是**对象**类型。  
  
-   您可以将 null 作为非值类型的参数的参数传递，但是可能会产生运行时错误，这取决于成员的实现情况。  
  
-   你可以设置字段的类型派生自**对象**为 null。  
  
## <a name="data-connection"></a>数据连接  
 以下情况适用于数据连接：  
  
-   如果表允许空值的列和列类型不是，你可以比较为 null，任何数据库表列**文本**， **ntext**，和**映像**。  
  
    > [!NOTE]
    >  业务规则编辑器，可使用的类型，列**文本**和**ntext**，在条件中。 但是，您执行该策略时将会收到错误消息，指出：“text、ntext、和 image 数据类型不能比较或排序，除非使用 IS NULL 或 LIKE 运算符”。  
  
-   如果数据库表允许列具有 null 值，则可以将该表的任何列设置为 null。  
  
-   业务规则编辑器会自动设置到绑定中的成员类型**对象**，如果比较或将设置为 null 的值类型; 它可以将其更改回原始类型如果重置或替换自变量。  
  
-   对于字符串类型，它更改为的类型**对象**如果将其设置为 null，但将其保留为一个字符串，如果比较结果为 null。  
  
-   不能比较或将设置为**DBNull.Value**从业务规则编辑器，因为它不会更改的列类型**对象**。  
  
-   该引擎会将 DBNull 值转换为 null 以便进行比较，并将 null 值转换为 DBNull 值以便插入到数据库中。  
  
-   测试将忽略 null 值（这是 SQL Server 的工作方式）。 例如，如果您有规则“IF db.column > 5 THEN”，则只测试 db.column 中具有值的行，跳过含 null 值的行。  
  
## <a name="typeddatatable-and-typeddatarow"></a>TypedDataTable 和 TypedDataRow  
 以下情况适用于 TypedDataTable 和 TypedDataRow：  
  
-   业务规则编辑器更改的字段类型**对象**中与使用相同的方式**该组**s。  
  
-   如果是 null 值，则测试将失败；除非与 null 进行比较。 例如，如果添加的任何行具有 null 值，则规则“IF db.column > 5 THEN”中将会生成错误。  
  
     请注意，由于条件是并行计算的，像“IF db.column != NULL AND db.column > 5 THEN”这样的测试仍会失败，这是因为两个测试在每行中可能都会进行评估。  
  
## <a name="checking-for-null-or-existence"></a>检查是否存在  
 编写业务规则时，在比较字段的值之前检查该字段是否存在是很正常的。 但是，如果该字段为 null（即不存在），则比较该值将引起错误。 假定存在以下规则：  
  
 如果产品/数量存在 AND 产品/数量 > 1  
  
 如果 Product/Quantity 不存在，规则中将引发错误。 规避此问题的方法之一是将父节点传递到 helper 方法，如果元素值存在，helper 方法将返回元素值；如果元素值不存在，则返回其他内容。 请参阅以下规则。  
  
 **规则 1**  
  
 IF EXISTS(Product/Quantity) THEN ASSERT(CREATEOBJECT(typeof(Helper), Product/Quantity)  
  
 **规则 2**  
  
 IF Helper.Value == X THEN...  
  
 另一个可能的解决方案是创建以下规则：  
  
 IF Product/Quantity Exist Then CheckQuantityAndDoSomething(Product/Quantity)  
  
 在上例中，CheckQuantityAndDoSomething 函数将会检查参数值，如果条件满足则执行该函数。  
  
> [!NOTE]
>  或者，你可以修改 XPath**字段**XML 事实来捕获任何错误，但它的属性不是建议的方法。