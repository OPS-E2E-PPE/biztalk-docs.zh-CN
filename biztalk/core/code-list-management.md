---
title: 代码列表管理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a924c814-d077-4aea-bacb-bf2e8a3dee01
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a28126d7acdb7e5d97b6aaa9924cea455c5fad1
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37010726"
---
# <a name="code-list-management"></a>代码列表管理

## <a name="overview"></a>概述
使用 XSD 可以为元素或属性指定特定的一组有效值。 此功能，则可使用**枚举**元素。 派生的数据类型时**Field 元素**或**Field 特性**通过限制，则可以在属性之一的节点**限制**类别是**枚举**属性。 使用此属性，可以打开**枚举编辑器**对话框可以在其中输入应被视为有效的相应元素或属性在实例消息中的值。  

 Microsoft BizTalk Server 提供了另一种管理架构中的枚举的方法，即代码列表，此方法的功能更为丰富。 代码列表使用 Microsoft Access 数据库来存储各种枚举选项，从而允许您以更加集中的方式管理枚举。 此外，如果您需要使用的枚举值包含的非直观的数字代码，将需要以该形式输入**枚举**属性中，Access 数据库用于代码列表中创建的表功能包括这些数值的文字说明。 在中使用文字说明**CodeList**对话框而不是其更模糊的等效数值。  

## <a name="use-the-code-list"></a>使用代码列表  
 必须执行以下多个不同步骤以使用代码列表功能：  

- 必须创建一个 Access 数据库，该数据库包含具有相应名称和所需列的表，然后使用相应值填充该表。  

  - 表的名称是的组合**标准**并**标准版本**的属性**架构**节点，以下划线 (_) 字符分隔。 例如，如果设置了**标准**的属性**架构**到 XML 节点和**标准版本**MyVersion1，通过指定的 Access 数据库的属性**代码列表数据库**属性必须具有名为 XML_MyVersion1 的表。  

    这些属性的更多详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

  - 此表必须包含三列，通常名为“代码”、“值”和“说明”。第一列标识与，其中每个此类行提供了一种可能对应于所选的数据允许在枚举选项相关的行**Field 元素**或**字段属性**节点。 第一列中具有相同值的所有行将构成一组。 这些值通常为整数，但也可以为不包含空格的任何字符串。  

     该表中每一行的第二列和第三列必须分别配置为包含与每个可能的枚举值相对应的值和文字说明。  

     例如，以下显示了一个用于代码列表功能的 Access 数据库表，其中包含了两组枚举值，每组中有三个相关的枚举值。 第一列中的特定值可以为任意值，并用于将相关行相关联。  


    | 代码 | ReplTest1 |  Desc  |
    |------|-------|--------|
    |  @shouldalert   |  13   |  Red   |
    |  @shouldalert   |  16   | 绿色  |
    |  @shouldalert   |  19   |  蓝色  |
    |  2   |   @shouldalert   | 小  |
    |  2   |   2   | Medium |
    |  2   |   3   | 大  |


- 必须正确配置的三个属性**架构**节点：  

  -   **代码列表数据库**属性必须设置为已创建的 Access 数据库的名称。  

  -   **标准**并**标准版本**必须设置属性，以便当它们组合在一起的分隔开来将下划线 (_) 字符，它们构成中指定的相应表的名称访问数据库。  

- 要实际做出选择特定的 Access 数据库中的值使用**字段元素**或**字段属性**节点，必须配置其两个属性：  

  -   必须设置其**Derived By**属性设置为**限制**。 若要配置，您需要的其他属性**CodeList**，只有在执行此步骤后将不会启用。  

  -   必须键入值**CodeList**对应于第一列中值的属性 (**代码**列) 的一个或多个行中指定的 Access 数据库。 此操作将标识你想要具有对应于所选的枚举值的一套**Field 元素**或**字段属性**节点。  

       然后，您必须单击省略号 (**...**) 按钮位于右侧的**CodeList**属性值字段中，打开**代码列表**对话框。 在此对话框中，使用对应的复选框选择想要允许作为合法值对应于所选的实例消息数据的值**Field 元素**或**字段属性**节点。 您可以只选择一部分可用值。 如果键入值 1，例如，就使用前面的表的示例中， **CodeList**属性，**代码列表**对话框将包含红色、 绿色和蓝色的选择。 如果您选中红色和绿色的复选框，并没有为蓝色选中此复选框，只有前两种颜色将显示在 XSD 中为有效的值为所选**Field 元素**或**字段属性**节点。  

> [!NOTE]
>  **CodeList**并**代码列表数据库**属性只能在设计时使用和保存到 XSD 中的相应设置为**枚举**属性。 在运行时，所有值来都验证对**枚举**只属性。  

> [!CAUTION]
>  为给定**Field 元素**或**Field 特性**节点，不要同时使用**枚举**属性和**代码列表**属性。 使用后一属性将会导致覆盖使用前一属性输入的值。  

## <a name="see-also"></a>请参阅  
 [创建架构时的注意事项](../core/considerations-when-creating-schemas.md)