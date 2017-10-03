---
title: "如何将 BizTalk Framework 反汇编程序管道组件配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, BizTalk Framework Disassembler
- disassembly stage, pipelines
- receive pipelines, disassembly stage
- BizTalk Framework Disassembler [pipeline component], configuring
ms.assetid: a5599bcb-dbee-46a5-a91d-3c54f901cd30
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 07fefb577e5322fa303a1a1476a976b453adb083
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-biztalk-framework-disassembler-pipeline-component"></a>如何将 BizTalk Framework 反汇编程序管道组件配置
BizTalk 框架拆装器管道组件应在接收管道的拆装阶段使用。  
  
### <a name="to-configure-the-properties-for-the-biztalk-framework-disassembler-pipeline-component"></a>配置 BizTalk 框架拆装器管道组件的属性  
  
1.  将 BizTalk 框架拆装器管道组件拖入接收管道的拆装阶段。  
  
2.  在属性窗口中，在**管道组件属性**部分中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**允许无法识别的消息**|指示是否允许不具有可识别的架构通过反汇编程序传递的消息。<br /><br /> 默认值： **False**|  
    |**文档架构**|指明要应用于文档的一个或多个架构的命名空间和类型名。 有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。<br /><br /> 此属性中指定的架构应具有唯一目标命名空间。 如果有任何架构的命名空间与之相同，则对文档实例的验证将可能无法按预期方式工作。 如果多个架构必须使用同一命名空间，则应为每个架构创建单独的管道，并为每个 BizTalk 框架拆装器管道组件指定一个架构，或者使用一个管道但不将任何架构指定为 BizTalk 框架拆装器管道组件的参数。<br /><br /> 默认值：空集合|  
    |**信封架构**|指明要应用于信封的一个或多个架构的命名空间和类型名。 有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。<br /><br /> 此属性中指定的架构应具有唯一目标命名空间。 如果有任何架构的命名空间与之相同，则对文档实例的验证将可能无法按预期方式工作。 如果多个架构必须使用同一命名空间，则应为每个架构创建单独的管道，并为每个 BizTalk 框架拆装器管道组件指定一个架构，或者使用一个管道但不将任何架构指定为 BizTalk 框架拆装器管道组件的参数。<br /><br /> 默认值：空集合|  
    |**验证文档结构**|当**True**，执行到反汇编程序，包括包络线的传入消息验证。 **注意：**时**True**，如果你指定两个或多个架构，可能会收到"两个或多个所选架构共享相同的目标命名空间"的错误**文档架构**或**信封架构**属性。 <br /><br /> 默认值： **False**|  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Framework 反汇编程序管道组件](../core/biztalk-framework-disassembler-pipeline-component.md)   
 [配置本机管道组件](../core/configuring-native-pipeline-components.md)   
 [管道 AssemblerDisassembler （BizTalk Server 示例文件夹中）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)   
 [配置本机管道组件](../core/configuring-native-pipeline-components.md)