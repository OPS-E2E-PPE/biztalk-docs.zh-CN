---
title: 如何处理 Null 和 DBNull |Microsoft Docs
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
ms.openlocfilehash: ea5635e289ce1d510e7e2701c79eeb3c9543b54e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385012"
---
# <a name="how-to-handle-null-and-dbnull"></a>如何处理 Null 和 DBNull
本主题介绍处理与不同类型的 null 值时的预期的行为，并讨论用于检查存在特定字段或成员的选项。  
  
## <a name="xml"></a>XML  
 以下情况适用于 XML:  
  
-   XML 值将永远不会返回从文档为 null。 它是空字符串或"不存在"错误。 空字符串时，错误可能会发生转换特定类型，例如，在生成规则时指定的整数类型的字段。  
  
-   业务规则编辑器不允许您将字段设置为 null 或设置到字段的类型**对象**。  
  
-   通过对象模型中，您可以设置类型为**对象**。 在这种情况下，返回的值是 XPath 计算结果的类型 — **float**，**布尔**，或**字符串**，取决于 XPath 表达式。  
  
## <a name="net-classes"></a>.NET 类  
 以下内容适用于.NET 类：  
  
-   您不能与 null 进行比较，如果返回类型不是**对象**类型。  
  
-   您可以将 null 作为传递的参数的参数不是值类型，但可能会收到运行时错误，具体取决于成员的实现。  
  
-   您可以设置字段的类型派生自**对象**为 null。  
  
## <a name="data-connection"></a>数据连接  
 以下内容适用于数据连接：  
  
-   如果允许空值的列和列类型不是，您可以比较为 null，任何数据库表列**文本**， **ntext**，并**图像**。  
  
    > [!NOTE]
    >  业务规则编辑器，可使用的类型，列**文本**并**ntext**，在条件中。 但是，在执行策略时，你将收到错误消息，指出:"text、 ntext 和 image 数据类型不能比较或排序，除非使用 IS NULL 或 LIKE 运算符"。  
  
-   如果允许空值的列，可以为 null，设置任何数据库表的列。  
  
-   业务规则编辑器会自动将绑定中设置的成员类型**对象**，如果比较或将设置为值类型，则为 null; 如果重置或替换该参数，它更改回原始类型。  
  
-   对于字符串类型，它更改为的类型**对象**如果将其设置为 null，但将其保留为一个字符串，如果与 null 进行比较。  
  
-   不能比较或将设置为**DBNull.Value**从业务规则编辑器中，因为它不会更改为的列类型**对象**。  
  
-   引擎会将 DBNull 值转换为 null 以便进行比较，并会将 null 转换为 DBNull 值以便插入到数据库。  
  
-   测试将忽略 null 值 （这是 SQL Server 的工作的方式）。 例如，如果您有规则"IF db.column > 5 THEN。"，测试 db.column 中具有值的行，为 null 的行被跳过。  
  
## <a name="typeddatatable-and-typeddatarow"></a>TypedDataTable 和 TypedDataRow  
 以下内容适用于 TypedDataTable 和 TypedDataRow:  
  
-   业务规则编辑器更改字段类型为**对象**中与使用相同的方式**DataConnection**s。  
  
-   除非与 null 进行比较，测试将失败的 null 值。 例如，将有一个错误在规则中"IF db.column > 5 THEN"，如果添加的任何行具有 null 值。  
  
     请注意，条件并行计算的因为测试类似于"IF db.column ！ = NULL AND db.column > 5 THEN"仍会失败，因为这两个测试的每一行上可能都会进行评估。  
  
## <a name="checking-for-null-or-existence"></a>检查存在  
 在编写业务规则时，是自然会检查存在的字段之前，请将其值进行比较。 但是，如果该字段为 null 或不存在，则将值进行比较将导致错误。 假设具有以下规则：  
  
 如果 Product/Quantity 存在 AND Product/Quantity > 1  
  
 如果 Product/Quantity 不存在，将在规则中引发错误。 要解决此问题的方法之一是将父节点传递到返回元素值，如果存在，或如果不是其他内容的帮助器方法。 请参阅下面的规则。  
  
 **规则 1**  
  
 如果 EXISTS(Product/Quantity) 然后 ASSERT(CREATEOBJECT(typeof(Helper)，产品/数量)  
  
 **规则 2**  
  
 IF Helper.Value == X THEN...  
  
 另一个可能的解决方案是创建的规则如下所示：  
  
 如果 Product/Quantity 存在然后 CheckQuantityAndDoSomething(Product/Quantity)  
  
 在前面的示例中，CheckQuantityAndDoSomething 函数将检查参数值并执行如果满足该条件。  
  
> [!NOTE]
>  或者，可以修改 XPath**字段**属性 XML 事实来捕获任何错误，但它不是建议的方法。