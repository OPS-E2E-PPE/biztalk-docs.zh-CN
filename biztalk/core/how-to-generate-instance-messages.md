---
title: 如何生成实例消息 |Microsoft Docs
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
ms.openlocfilehash: 0f851a2888fe0dd9a82b86a47d2ca8faa42c8edf
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385042"
---
# <a name="how-to-generate-instance-messages"></a>如何生成实例消息
构造架构之后，检查您的工作的一种方法是从架构生成示例实例消息。 在许多方面，查看实例消息是架构的比查看架构树或 XML 架构定义 (XSD) 语言表示的要简单得多。 这是因为架构需要描述相应实例消息中，可能变体的所有，特定的实例消息只需通过使用由架构指定的格式，提供一些数据。 生成的实例消息是一个示例，可能不会显示所有由相应的架构定义的结构。  
  
### <a name="to-explicitly-specify-a-file-to-contain-the-generated-instance-message"></a>若要显式指定要包含生成的实例消息的文件  
  
1.  在解决方案资源管理器，右键单击要为其生成实例消息，然后单击的架构**属性**。  
  
2.  如有必要，在属性窗口中，展开**常规**一部分**常规**选项卡上，通过单击其加号 （+） 图标。  
  
3.  在中**输出实例文件名**属性值字段中，键入文件的名称，或使用省略号 (**...**) 按钮以浏览的文件生成的实例消息将放置到其中，然后单击值字段右侧**保存**。  
  
### <a name="to-specify-the-type-of-the-generated-instance-message"></a>若要指定生成的实例消息的类型  
  
1.  在解决方案资源管理器，右键单击要为其生成实例消息，然后单击的架构**属性**。  
  
2.  如有必要，在属性窗口中，展开**常规**一部分**常规**选项卡上，通过单击其加号 （+） 图标。  
  
3.  在中**生成实例输出类型**属性值字段中，使用下拉列表选择**XML**或**本机**作为要生成的实例消息的类型。  
  
     **XML**是默认值。  
  
### <a name="to-generate-a-sample-instance-message-for-a-schema"></a>若要生成示例实例消息的架构  
  
1.  在解决方案资源管理器，右键单击要为其生成实例消息，然后单击的架构**生成实例**。  
  
2.  在输出窗口中查看结果。 在此窗口中显示成功和错误消息。  
  
> [!NOTE]
>  如果输出窗口和/或任务列表窗口并未打开与显示有关的信息生成了实例是成功还是失败，您可以手动打开。 有关管理这些窗口的详细信息，请参阅[管理其他 Visual Studio Windows](../core/how-to-manage-other-visual-studio-windows.md)。  
  
> [!NOTE]
>  如果未指定的值**根引用**属性，BizTalk 编辑器架构中生成示例实例消息的第一个根节点。 如果指定的值**根引用**属性，BizTalk 编辑器生成该根的示例实例消息。  
  
> [!NOTE]
>  有一些情况下实例中的特定架构生成消息可能无法通过使用该相同的架构进行验证。 有关这种情况下的详细信息，请参阅[架构生成和验证的已知问题](../core/known-issues-with-schema-generation-and-validation.md)。 通常情况下，你想要编辑生成的实例消息并将更改，使其更真实地表示你的方案及其包含的数据。 然后使用此修改后的实例消息来验证您的架构。  
  
## <a name="see-also"></a>请参阅  
 [测试架构](../core/testing-schemas.md)   
 [架构验证](../core/schema-validation1.md)   
 [实例消息的生成和验证](../core/instance-message-generation-and-validation.md)