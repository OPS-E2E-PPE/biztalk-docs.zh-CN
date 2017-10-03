---
title: "如何配置转换形状 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring [Orchestration Designer], Transform shape
- Transform shape [Orchestration Designer]
ms.assetid: ca81d153-77a6-4bcc-b14f-8f48469fffe0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48cdca50620262581469e924fbb2975dde7e91fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-transform-shape"></a>如何配置转换形状
![](../core/media/ebiz-orch-transform.gif "ebiz_orch_transform")  
转换形状 (Transform shape)  
  
 转换只用于在构造消息，因此你**转换**形状显示方式始终内**构造消息**形状。 可以删除**构造消息**调整设计图面上，然后将放**转换**形状内，或者也可以只需删除**转换**对该设计的形状图面，并创建封闭的业务流程设计器将**构造消息**为你的形状。  
  
> [!NOTE]
>  中的任何源或目标消息**转换**必须基于架构。  
  
## <a name="procedure"></a>过程  
  
#### <a name="to-configure-a-transform-shape"></a>配置转换形状  
  
1.  在属性窗口中，单击**省略号**(**...**) 按钮**输入消息**，**输出消息**，或**映射名称**属性。  
  
2.  使用**转换配置**对话框配置**转换**形状。  
  
> [!NOTE]
>  A**转换**形状可以仅在存在**构造消息**形状。 如果将拖动**消息分配**调整设计图面上的其他任何位置新**构造消息**将创建形状。  
  
### <a name="important-performance-considerations"></a>重要的性能注意事项  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可优化大型消息上执行转换，通过将应用而不是在一次加载到内存的整个文档转换时到内存流文档的能力。 这种优化允许对比早期版本的 BizTalk Server 所允许的文档大得多的文档进行映射/转换。 如果业务流程为转换形状接受多个输入和/或输出，则会限制这一优化。  
  
 如果业务流程为转移形状接受多个输入和/或输出，则不执行文档流式处理，并且内存使用量会大幅增加。 此问题的一种可能的解决方法是，在接收管道中应用单个或多个转换，使业务流程不再为转换形状接受多个输入或多个输出。  
  
### <a name="newexisting-map-file"></a>是新建映射文件还是现有映射文件？  
 在此部分中，可以单击**新图**或**现有映射**选项按钮以选择要分配给一个映射**转换**形状。  
  
 使用**名称**字段在选定的选项按钮以指定地图的下面。 如果你选择**新图**，您可以键入你想要分配映射指定内容。 当你使用**新图**选项，你必须在文本框中指定映射的完全限定的名称。 文本框中默认情况下，显示举例说明这样的名称，因为它是基于项目命名空间的唯一标识符名称预填充和**转换**形状名称：\<项目命名空间 >。\<转换形状名称 > _Map (例如，MyProject.Transform3_Map)。  
  
 如果你选择**现有映射**，单击中的向下箭头**名称**字段来选择要使用的映射文件。 此列表框会显示该项目中可用的所有现有映射的列表（按字母顺序排序）。 在此列表中，如果您单击文本\<选择从引用的程序集 >，则**选择项目类型**对话框随即显示。 它使可选择的详细信息，请参阅[如何使用选择项目类型对话框中](../core/how-to-use-the-select-artifact-type-dialog-box.md)。  
  
### <a name="select-source-and-destination-messages"></a>选择源消息和目标消息  
 使用这一部分**转换配置**对话框可以配置在所选的映射**新建/现有映射文件？**部分。 如果你选择**新图**在该部分中，创建该图通过将其配置在本部分中。  
  
 如果你选择**现有映射**，你可以使用本部分执行两个操作之一：  
  
-   选择一个现有映射，在当前转换中按原样重新使用。  
  
-   选择一个现有映射以便对它进行更改（配置），然后在当前转换的新配置中使用该映射。  
  
 通过使用指定源和目标消息**源消息**和**目标消息**网格控件。 可以使用这些网格控件以多种方式更改映射文件。 如果删除的消息（任一网格控件中的一行）、添加的消息或选择的消息是另一种类型，则会改变映射的结构。 改变映射的结构后，必须更改使用此映射的所有其他转换，使其与映射的新结构相匹配。 其他更改（如删除一个消息并在其位置插入同种类型的消息）不会改变映射的结构。  
  
 **源消息**和**目标消息**网格控件是在外观和行为完全相同。 每个网格控件都有两列：消息和类型。 通过在消息列中选择消息来填充网格控件。 （数据只能添加到消息列中，因为类型列是只读的。）消息列中的单元格具有下拉列表，其中填充了当前业务流程范围内的消息实例。  
  
 可以通过单击任一网格控件中选择一行*右箭头*网格控件的左侧 (>) 按钮。 选定一行后，可以按 Delete 键删除此行。 删除一行（一个消息）会改变包含此行的映射文件的结构。 只能修改项目的本地映射文件。  
  
### <a name="when-i-click-ok-launch-the-biztalk-mapper"></a>单击“确定”即启动 Biztalk 映射器  
 单击**时我单击确定，启动 BizTalk 映射程序**将 BizTalk 映射程序自动打开，当你单击**确定**关闭**转换配置**对话框框中，并保存所做的更改。 但如果必需的信息丢失，则无法保存更改。 在这种情况下，完成填写对话框中的字段，然后单击**确定**。  
  
## <a name="see-also"></a>另请参阅  
 [有关映射](../core/about-maps.md)   
 [构造消息](../core/constructing-messages.md)   
 [如何使用动态转换消息的表达式](../core/how-to-use-expressions-to-dynamic-transform-messages.md)