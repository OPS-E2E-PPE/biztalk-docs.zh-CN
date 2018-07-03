---
title: 如何配置转换形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Orchestration Designer], Transform shape
- Transform shape [Orchestration Designer]
ms.assetid: ca81d153-77a6-4bcc-b14f-8f48469fffe0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc88110940626602059466324d0dc38e59f88afe
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980966"
---
# <a name="how-to-configure-the-transform-shape"></a>如何配置转换形状
![](../core/media/ebiz-orch-transform.gif "ebiz_orch_transform")  
转换形状 (Transform shape)  
  
 在构造消息，因此时才使用转换您**转换**形状内始终将显示**构造消息**形状。 可以删除**构造消息**设计图面上形状，然后再删除**转换**形状内，或者也可以只是删除**转换**在设计上的形状图面上，并创建封闭的业务流程设计器将**构造消息**为你的形状。  
  
> [!NOTE]
>  中的任何源或目标消息**转换**必须基于架构。  
  
## <a name="procedure"></a>过程  
  
#### <a name="to-configure-a-transform-shape"></a>配置转换形状  
  
1.  在属性窗口中，单击**省略号**(**...**) 按钮**输入消息**，**输出消息**，或**映射名称**属性。  
  
2.  使用**转换配置**对话框可以配置**转换**形状。  
  
> [!NOTE]
>  一个**转换**形状可以仅在存在**构造消息**形状。 如果您拖动**消息赋值**形状在设计图面上的其他任何位置的新**构造消息**将创建形状。  
  
### <a name="important-performance-considerations"></a>重要的性能注意事项  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 优化了对大消息执行转换，通过将文档流式处理到内存中同时应用转换，而不是一次性将整个文档加载到内存的能力。 这种优化允许对比早期版本的 BizTalk Server 所允许的文档大得多的文档进行映射/转换。 如果业务流程为转换形状接受多个输入和/或输出，则会限制这一优化。  
  
 如果业务流程为转移形状接受多个输入和/或输出，则不执行文档流式处理，并且内存使用量会大幅增加。 此问题的一种可能的解决方法是，在接收管道中应用单个或多个转换，使业务流程不再为转换形状接受多个输入或多个输出。  
  
### <a name="newexisting-map-file"></a>是新建映射文件还是现有映射文件？  
 在本部分中，可以单击**新的映射**或**现有映射**选项按钮以选择要分配给一个映射**转换**形状。  
  
 使用**名称**字段可指定映射在所选的选项按钮的下面。 如果所选**新的映射**，可以键入你想要分配的映射的名称。 当你使用**新的映射**选项，必须在文本框中指定映射的完全限定的名称。 在文本框中默认情况下显示此类名称的一个示例，因为它是基于项目命名空间的唯一标识符名称预先填充和**转换**形状名称：\<项目命名空间\>。\<转换形状名称\>_Map (例如，MyProject.Transform3_Map)。  
  
 如果所选**现有的映射**，单击中的下箭头**名称**字段来选择要使用的映射文件。 此列表框会显示该项目中可用的所有现有映射的列表（按字母顺序排序）。 在此列表中，如果单击文本\<从引用的程序集中\>，则**选择项目类型**显示对话框。 可通过其所选内容的详细信息，请参阅[如何使用选择项目类型对话框中](../core/how-to-use-the-select-artifact-type-dialog-box.md)。  
  
### <a name="select-source-and-destination-messages"></a>选择源消息和目标消息  
 使用此部分**转换配置**对话框可以配置在选定的映射**新建还是现有映射文件？** 部分。 如果所选**新的映射**部分中，创建映射通过在本部分中配置。  
  
 如果所选**现有的映射**，可以使用本部分中执行两项操作之一：  
  
- 选择一个现有映射，在当前转换中按原样重新使用。  
  
- 选择一个现有映射以便对它进行更改（配置），然后在当前转换的新配置中使用该映射。  
  
  使用指定源和目标消息**源消息**并**目标消息**网格控件。 可以使用这些网格控件以多种方式更改映射文件。 如果删除的消息（任一网格控件中的一行）、添加的消息或选择的消息是另一种类型，则会改变映射的结构。 改变映射的结构后，必须更改使用此映射的所有其他转换，使其与映射的新结构相匹配。 其他更改（如删除一个消息并在其位置插入同种类型的消息）不会改变映射的结构。  
  
  **源消息**并**目标消息**网格控件是相同的外观和行为。 每个网格控件都有两列：消息和类型。 通过在消息列中选择消息来填充网格控件。 （数据只能添加到消息列中，因为类型列是只读的。）消息列中的单元格具有下拉列表，其中填充了当前业务流程范围内的消息实例。  
  
  可以通过单击任一网格控件中选择某一行*向右箭头*(>) 按钮，位于左侧和右侧的网格控件。 选定一行后，可以按 Delete 键删除此行。 删除一行（一个消息）会改变包含此行的映射文件的结构。 只能修改项目的本地映射文件。  
  
### <a name="when-i-click-ok-launch-the-biztalk-mapper"></a>单击“确定”即启动 Biztalk 映射器  
 单击**当我单击确定时，启动 BizTalk 映射器**单击时自动打开 BizTalk 映射器**确定**以关闭**转换配置**对话框框中并保存所做的更改。 但如果必需的信息丢失，则无法保存更改。 在这种情况下，完成填写对话框框中的字段，然后单击**确定**。  
  
## <a name="see-also"></a>请参阅  
 [有关地图](../core/about-maps.md)   
 [构造消息](../core/constructing-messages.md)   
 [如何使用表达式来动态转换消息](../core/how-to-use-expressions-to-dynamic-transform-messages.md)