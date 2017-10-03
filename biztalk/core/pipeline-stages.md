---
title: "管道阶段 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipelines, properties
- CATID_AssemblingSerializer component category
- CATID_Encoder component category
- pipelines, stages
- CATID_DisassemblingParser component category
- CATID_Validate component category
- ComponentCategory class attribute
- CATID_Decoder component category
- CATID_Any component category
- CATID_PartyResolver component category
- Execution Mode property
ms.assetid: ac50c48c-6ed5-4322-95cc-af55df6bcd1c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aeb675f39cb39ade4230e6e39f798e95115aaf78
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="pipeline-stages"></a>管道阶段
本主题讨论**执行模式**属性和阶段相关性。  
  
## <a name="execution-mode-property"></a>“执行模式”属性  
 在管道的执行期间，管道阶段只能运行第一个识别消息格式的组件或所有组件。 属性，用于确定执行模式是**执行模式**。  
  
> [!NOTE]
>  此属性在管道模板包括的阶段中是只读的，但了解其工作原理非常重要。  
  
 当**执行模式**属性设置为**所有**，阶段内的所有组件都运行配置的序列中。 此模式运行多个组件来完成一项逻辑任务。 在这种情况下，如果任何组件在此管道阶段处理消息过程中遇到错误，都会导致运行时错误。  
  
 当管道用于接收消息的几种格式，则**执行模式**属性设置为**匹配**。 在此模式下，只运行第一个识别消息的组件。 如果阶段中没有组件可识别消息，则会导致运行时错误。  
  
 请注意，每个阶段都有其自己**执行模式**在管道中的设置，因此不同阶段可具有不同的执行模式。  
  
> [!NOTE]
>  在此版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]、 管道中发送的所有阶段和拆卸除外的所有阶段，接收都管道中都具有的值**执行模式**属性设置为**所有**。 值**执行模式**拆装阶段中的属性设置为**匹配**。 无法更改**执行模式**阶段的属性。  
  
#### <a name="to-read-pipeline-stage-properties"></a>查看管道阶段属性  
  
1.  在管道设计器中，单击相应的阶段形状。  
  
2.  在属性窗口中，在**常规**部分中，读取的以下属性：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|指示阶段的名称。|  
    |**执行模式**|指示阶段的执行模式。<br /><br /> 有效值：**所有**或**匹配**|  
    |**组件的最小数目**|指示可向阶段添加的最小管道组件数。|  
    |**组件的最大数目**|指示可向阶段添加的最大管道组件数。|  
    |**StageID**|指示阶段的唯一标识符。|  
  
## <a name="stage-affinity"></a>阶段关联  
 管道组件有阶段关联，这意味着管道组件是为在管道中特定的一个或多个阶段中使用而创建的。  
  
 基于 COM 的管道组件通过注册本身作为实现类别中，使用阶段 ID express 其阶段相关性时。基于网络的管道组件通过指定其阶段相关性**ComponentCategory**类特性。 请注意，可能要将其自身与多个阶段相关联的组件，组件可以具有多个实现类别或**ComponentCategory**属性。  
  
 下表显示了可用的组件类别及其关联阶段：  
  
|组件类别|可放置组件的阶段|Description|  
|------------------------|-----------------------------------------|-----------------|  
|CATID_Decoder {9d0e4103-4cce-4536-83fa-4a5040674ad6}|解码|所有解码组件都应实现此类别。|  
|CATID_DisassemblingParser {9d0e4105-4cce-4536-83fa-4a5040674ad6}|拆装|所有拆装组件和解析组件都应实现此类别。|  
|CATID_Validate {9d0e410d-4cce-4536-83fa-4a5040674ad6}|验证|验证组件应实现此类别。|  
|CATID_PartyResolver {9d0e410e-4cce-4536-83fa-4a5040674ad6}|解析参与方|用于参与方解析组件的阶段。|  
|CATID_Encoder {9d0e4108-4cce-4536-83fa-4a5040674ad6}|编码|所有编码组件都应实现此类别。|  
|CATID_AssemblingSerializer {9d0e4107-4cce-4536-83fa-4a5040674ad6}|序列化|所有序列化组件和组装组件都应实现此类别。|  
|CATID_Any {9d0e4101-4cce-4536-83fa-4a5040674ad6}|这些阶段中的任意阶段|如果某管道组件实现了此类别，则意味着该组件可以放置在管道的任意阶段中。|  
  
## <a name="see-also"></a>另请参阅  
 [创建管道使用管道设计器](../core/creating-pipelines-using-pipeline-designer.md)   
 [有关管道、 阶段和组件](../core/about-pipelines-stages-and-components.md)