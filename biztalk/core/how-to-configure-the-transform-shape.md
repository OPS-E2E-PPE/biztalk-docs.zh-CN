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
ms.openlocfilehash: 7c813505481fd0331a5e5f229b6007a0a773a1f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340302"
---
# <a name="how-to-configure-the-transform-shape"></a>如何配置转换形状
![](../core/media/ebiz-orch-transform.gif "ebiz_orch_transform")  
转换形状  
  
 在构造消息，因此时才使用转换您**转换**形状内始终将显示**构造消息**形状。 可以删除**构造消息**设计图面上形状，然后再删除**转换**形状内，或者也可以只是删除**转换**在设计上的形状图面上，并创建封闭的业务流程设计器将**构造消息**为你的形状。  
  
> [!NOTE]
>  中的任何源或目标消息**转换**必须基于架构。  
  
## <a name="procedure"></a>过程  
  
#### <a name="to-configure-a-transform-shape"></a>若要配置转换形状  
  
1.  在属性窗口中，单击**省略号**(**...**) 按钮**输入消息**，**输出消息**，或**映射名称**属性。  
  
2.  使用**转换配置**对话框可以配置**转换**形状。  
  
> [!NOTE]
>  一个**转换**形状可以仅在存在**构造消息**形状。 如果您拖动**消息赋值**形状在设计图面上的其他任何位置的新**构造消息**将创建形状。  
  
### <a name="important-performance-considerations"></a>重要的性能注意事项  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 优化了对大消息执行转换，通过将文档流式处理到内存中同时应用转换，而不是一次性将整个文档加载到内存的能力。 这种优化允许大得多文档比早期版本的 BizTalk Server 映射/转换。 当业务流程接受多个输入和/或输出转换形状时，会发生这种优化的一个限制。  
  
 如果业务流程接受多个输入和/或输出转换形状，则不执行文档流式处理和内存使用量会大幅增加。 此问题的一种解决方法是，将转换或转换的接收管道中，以便该业务流程不会接受多个单个输入或单个输出为转换形状。  
  
### <a name="newexisting-map-file"></a>新的/现有映射文件？  
 在本部分中，可以单击**新的映射**或**现有映射**选项按钮以选择要分配给一个映射**转换**形状。  
  
 使用**名称**字段可指定映射在所选的选项按钮的下面。 如果所选**新的映射**，可以键入你想要分配的映射的名称。 当你使用**新的映射**选项，必须在文本框中指定映射的完全限定的名称。 在文本框中默认情况下显示此类名称的一个示例，因为它是基于项目命名空间的唯一标识符名称预先填充和**转换**形状名称：\<项目命名空间\>。\<转换形状名称\>_Map (例如，MyProject.Transform3_Map)。  
  
 如果所选**现有的映射**，单击中的下箭头**名称**字段来选择要使用的映射文件。 此列表框显示所有的现有映射的项目中提供的按字母顺序排序的列表。 在此列表中，如果单击文本\<从引用的程序集中\>，则**选择项目类型**显示对话框。 可通过其所选内容的详细信息，请参阅[如何使用选择项目类型对话框中](../core/how-to-use-the-select-artifact-type-dialog-box.md)。  
  
### <a name="select-source-and-destination-messages"></a>选择源和目标消息  
 使用此部分**转换配置**对话框可以配置在选定的映射**新建还是现有映射文件？** 部分。 如果所选**新的映射**部分中，创建映射通过在本部分中配置。  
  
 如果所选**现有的映射**，可以使用本部分中执行两项操作之一：  
  
- 选择现有的映射按原样重新使用的是在当前转换中。  
  
- 若要更改 （配置） 选择一个现有映射，并使用它在当前转换中的新配置。  
  
  使用指定源和目标消息**源消息**并**目标消息**网格控件。 可以使用这些网格控件来更改映射文件中有多种。 如果您删除一条消息 （任一网格控件中某行），添加一条消息，或选择不同类型的消息，您可以更改映射的结构。 当更改映射的结构时必须更改使用它的所有其他转换以匹配新映射的结构。 其他更改，如删除一个消息并在其位置插入一条消息的相同的类型，不会改变映射的结构。  
  
  **源消息**并**目标消息**网格控件是相同的外观和行为。 每个网格控件具有两个列：消息和类型。 通过选择消息列中的消息填充网格控件。 （您数据只能添加到消息列中，因为类型列是只读的。）在消息列中的单元格都具有下拉列表，其中填充了当前业务流程的作用域内的消息实例。  
  
  可以通过单击任一网格控件中选择某一行*向右箭头*(>) 按钮，位于左侧和右侧的网格控件。 选择某一行后，可以通过按 DELETE 键删除它。 删除行 （消息） 会改变包含此行的映射文件的结构。 可以修改项目的本地添加的映射文件。  
  
### <a name="when-i-click-ok-launch-the-biztalk-mapper"></a>当我单击确定时，启动 BizTalk 映射器  
 单击**当我单击确定时，启动 BizTalk 映射器**单击时自动打开 BizTalk 映射器**确定**以关闭**转换配置**对话框框中并保存所做的更改。 但是，如果信息缺少必需的则无法保存更改。 在这种情况下，完成填写对话框框中的字段，然后单击**确定**。  
  
## <a name="see-also"></a>请参阅  
 [有关地图](../core/about-maps.md)   
 [构造消息](../core/constructing-messages.md)   
 [如何使用表达式来动态转换消息](../core/how-to-use-expressions-to-dynamic-transform-messages.md)