---
title: 如何创建使用其他架构的架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff0bcd9a-6c66-4c3b-bd41-64047a7c8392
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 729e956fc2598fb8c3bd75d2d2d8a9613e1e96ac
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385440"
---
# <a name="how-to-create-schemas-that-use-other-schemas"></a>如何创建使用其他架构的架构
XML 架构定义 (XSD) 语言提供了三种不同但相关机制来使用一个架构中的其他架构。 这些机制导入架构，包括架构和重新定义架构。 有关这些机制以及它们之间的区别的简短摘要，请参阅[使用其他架构的](../core/schemas-that-use-other-schemas.md)。 有关详细信息，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)有关指向 XSD 基本知识和规范。  
  
 本主题介绍导入、 包括和重新定义其他架构内正在开发的架构所需的步骤。  
  
### <a name="to-import-include-or-redefine-one-schema-within-another-schema"></a>若要导入、 包括或重新定义一个架构中的其他架构  
  
1. 在 BizTalk 编辑器中，打开你想要导入、 包括或重新定义其他架构的架构。 可以通过双击解决方案资源管理器中打开架构。  
  
2. 选择**架构**节点在架构树视图的顶部。  
  
3. 如有必要，请按 F4 打开[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口。  
  
4. 在属性窗口中**高级**类别中的值部分**导入**属性中，单击省略号 (**...**) 按钮。  
  
5. 在中**导入**对话框中**作为新架构导入**列表中，选择**XSD 导入**， **XSD Include**，或**XSD重新定义**，根据需要，，然后单击**添加**。  
  
6. 在中**BizTalk 类型选取器**对话框框中，展开**架构**节点在项目树中，选择你想要导入、 包括或重新定义，，然后单击该架构**确定**。  
  
7. 在中**导入**对话框中，单击**确定**。  
  
    相应 XSD 指令来实现导入、 包括或重新定义操作添加到**架构**在 XSD 视图中，包括新的元素**导入**，**包括**，或**重新定义**元素中的，根据需要。  
  
> [!IMPORTANT]
>  请确保了解这三种机制，如有何不同命名空间要求方面的不同用途。 您可以始终删除以前导入、 包括或重新定义架构，然后使用一个其他两种机制，但具体取决于你如何广泛引用该架构，您可能需要相应地修改您的架构。  
  
> [!IMPORTANT]
>  导入、 包括和按引用导入、 重新定义一个架构中另一个架构工作原理的 XSD 机制包括或重新定义的架构。 这意味着，如果您更改导入、 包括或重新定义架构，该更改将反映在包含导入，架构中包括或重新定义引用。  
  
## <a name="see-also"></a>请参阅  
 [管理项目中的架构](../core/managing-schemas-within-projects.md)   
 [如何创建对其他节点或类型的引用](../core/how-to-create-references-to-another-node-or-type.md)