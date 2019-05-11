---
title: 如何配置 BizTalk 框架拆装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, BizTalk Framework Disassembler
- disassembly stage, pipelines
- receive pipelines, disassembly stage
- BizTalk Framework Disassembler [pipeline component], configuring
ms.assetid: a5599bcb-dbee-46a5-a91d-3c54f901cd30
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 46ce50dc68f7a11cd63c7244c9abcb6930a08f3f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341140"
---
# <a name="how-to-configure-the-biztalk-framework-disassembler-pipeline-component"></a>如何配置 BizTalk 框架拆装器管道组件
BizTalk 框架拆装器管道组件应在接收管道的拆装阶段中使用。  
  
### <a name="to-configure-the-properties-for-the-biztalk-framework-disassembler-pipeline-component"></a>若要配置 BizTalk 框架拆装器管道组件的属性  
  
1.  将 BizTalk 框架拆装器管道组件拖至接收管道的拆装阶段。  
  
2.  在属性窗口中**管道组件属性**部分中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**允许无法识别的消息**|指示是否允许没有可识别的架构通过拆装器传递的消息。<br /><br /> 默认值：**False**|  
    |**文档架构**|指示命名空间和类型名或多个架构应用于文档。 有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。<br /><br /> 此属性中指定的架构应具有唯一目标命名空间。 如果具有相同的命名空间的任何架构，对文档实例的验证可能不会按预期工作。 如果架构必须具有相同的命名空间，您应创建单独的管道为每个架构和指定每个 BizTalk 框架拆装器管道组件的一个架构，或使用一个管道但不是指定任何架构作为参数的 BizTalk框架拆装器管道组件。<br /><br /> 默认值：空集合|  
    |**信封架构**|指示命名空间和类型名或多个要应用于信封的架构。 有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。<br /><br /> 此属性中指定的架构应具有唯一目标命名空间。 如果具有相同的命名空间的任何架构，对文档实例的验证可能不会按预期工作。 如果架构必须具有相同的命名空间，您应创建单独的管道为每个架构和指定每个 BizTalk 框架拆装器管道组件的一个架构，或使用一个管道但不是指定任何架构作为参数的 BizTalk框架拆装器管道组件。<br /><br /> 默认值：空集合|  
    |**验证文档结构**|当 **，则返回 True**，执行的传入消息和拆装器，包括信封验证。 **注意：** 当 **，则返回 True**，如果指定两个或多个架构，可能会收到错误"两个或多个所选架构共享同一目标命名空间"**文档架构**或**信封架构**属性。 <br /><br /> 默认值：**False**|  
  
## <a name="see-also"></a>请参阅  
 [BizTalk 框架拆装器管道组件](../core/biztalk-framework-disassembler-pipeline-component.md)   
 [配置本地管道组件](../core/configuring-native-pipeline-components.md)   
 [Pipelines-assemblerdisassembler （BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)   
 [配置本地管道组件](../core/configuring-native-pipeline-components.md)