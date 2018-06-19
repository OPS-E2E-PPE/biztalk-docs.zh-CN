---
title: 如何生成实例消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff74c67a-7e73-4153-9ec4-e6e50464ee92
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a911e4b0f1167e8ec200dad65b8dacb94bb08be3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22254397"
---
# <a name="how-to-generate-instance-messages"></a>如何生成实例消息
构造架构之后，有一种检查工作的方法是从该架构生成一个实例消息示例。 在很多方法中，查看实例消息都比查看架构树或架构的 XML 架构定义 (XSD) 语言表示形式直接的多。 这是因为架构需要描述相应实例消息的所有可能变体，而特定的实例消息只需通过使用由架构指定的格式来传送某些数据。 生成的实例消息是一个示例，可能无法显示由相应架构定义的所有结构。  
  
### <a name="to-explicitly-specify-a-file-to-contain-the-generated-instance-message"></a>显式指定文件以包含生成的实例消息  
  
1.  在解决方案资源管理器，右键单击你要为其生成实例消息，并依次的架构**属性**。  
  
2.  如有必要，在属性窗口中，展开**常规**部分**常规**选项卡上通过单击其加号 （+） 图标。  
  
3.  在**输出实例文件名**属性值字段中，键入文件的名称，或者使用省略号 (**...**) 值字段来浏览的文件生成的实例消息将放置到其中，然后单击右侧的按钮**保存**。  
  
### <a name="to-specify-the-type-of-the-generated-instance-message"></a>指定生成的实例消息的类型  
  
1.  在解决方案资源管理器，右键单击你要为其生成实例消息，并依次的架构**属性**。  
  
2.  如有必要，在属性窗口中，展开**常规**部分**常规**选项卡上通过单击其加号 （+） 图标。  
  
3.  在**生成实例输出类型**属性值字段中，使用下拉列表中选择**XML**或**本机**作为实例消息生成的类型。  
  
     **XML**是默认值。  
  
### <a name="to-generate-a-sample-instance-message-for-a-schema"></a>生成架构的实例消息示例  
  
1.  在解决方案资源管理器，右键单击你要为其生成实例消息，并依次的架构**生成实例**。  
  
2.  在“输出”窗口中，查看结果。 此窗口中将显示成功消息和错误消息。  
  
> [!NOTE]
>  如果“输出”窗口和/或“任务列表”窗口并未打开与显示与实例生成成败与否相关的信息，则可以手动打开。 有关管理这些窗口的详细信息，请参阅[管理其他 Visual Studio 窗口](../core/how-to-manage-other-visual-studio-windows.md)。  
  
> [!NOTE]
>  如果未指定的值**根引用**属性，BizTalk 编辑器在架构中生成的第一个根节点的示例实例消息。 如果指定的值**根引用**属性，BizTalk 编辑器生成该根的示例实例消息。  
  
> [!NOTE]
>  在某些情况下，由特定架构生成的实例消息可能无法通过使用同一架构进行的验证。 有关这种情况下的详细信息，请参阅[已知架构生成和验证问题](../core/known-issues-with-schema-generation-and-validation.md)。 通常情况下，你想要编辑生成的实例消息并更改它所包含，使其更真实地表示你的方案的数据。 然后使用此修改的实例消息来验证您的架构。  
  
## <a name="see-also"></a>另请参阅  
 [测试架构](../core/testing-schemas.md)   
 [架构验证](../core/schema-validation1.md)   
 [实例消息生成和验证](../core/instance-message-generation-and-validation.md)