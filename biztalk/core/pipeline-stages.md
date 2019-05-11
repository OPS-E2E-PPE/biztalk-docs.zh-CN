---
title: 管道阶段 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3e24d6660e56bfbd44391b092152735f67fbb23
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395779"
---
# <a name="pipeline-stages"></a>管道阶段
本主题讨论**执行模式**属性和阶段关联。  
  
## <a name="execution-mode-property"></a>执行模式属性  
 执行过程中的管道，管道阶段可以运行仅识别消息格式的第一个组件或所有组件。 属性，用于确定执行模式是**执行模式**。  
  
> [!NOTE]
>  此属性在管道模板中包括的阶段上是只读的但了解其工作原理是一个重要概念。  
  
 当**执行模式**属性设置为**所有**，阶段中的所有组件中配置的顺序都运行。 此模式下运行多个组件完成一项逻辑任务。 在这种情况下，如果任何组件在此管道阶段处理消息时遇到错误会导致运行时错误。  
  
 当管道用于接收多种格式的消息，然后**执行模式**属性设置为**FirstMatch**。 在此模式下，运行仅识别该消息的第一个组件。 如果阶段中的没有组件可识别消息，会运行时错误。  
  
 请注意，每个阶段可以具有其自己**执行模式**在管道中的设置，因此不同阶段可以具有不同的执行模式。  
  
> [!NOTE]
>  在此版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，在发送中的所有阶段的都管道，并且除拆装的接收都管道中的所有阶段都具有的值**执行模式**属性设置为**所有**。 值**执行模式**拆装阶段中的属性设置为**FirstMatch**。 不能更改**执行模式**阶段的属性。  
  
#### <a name="to-read-pipeline-stage-properties"></a>若要查看管道阶段属性  
  
1.  在管道设计器中，单击的阶段形状。  
  
2.  在属性窗口中**常规**部分中，读取以下属性：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**名称**|指示阶段的名称。|  
    |**执行模式**|指示阶段的执行模式。<br /><br /> 有效的值：**所有**或**第一个匹配**|  
    |**最小组件数**|指示可向阶段添加管道组件的最小数目。|  
    |**最大组件数**|指示可向阶段添加管道组件的最大数目。|  
    |**StageID**|指示阶段的唯一标识符。|  
  
## <a name="stage-affinity"></a>阶段关联  
 管道组件有阶段关联，这意味着在创建某个特定阶段或管道中的阶段中使用。  
  
 基于 COM 的管道组件通过使用阶段 ID 作为实现类别中，将自己注册来表示它们的阶段关联时。基于 NET 的管道组件通过使用指定它们的阶段关联**ComponentCategory**类属性。 请注意，很可能要将自身与多个阶段相关联的组件，组件可以有多个实现类别或**ComponentCategory**属性。  
  
 下表显示了可用的组件类别和及其关联的阶段。  
  
|组件类别|何处可放置组件的阶段|Description|  
|------------------------|-----------------------------------------|-----------------|  
|CATID_Decoder {9d0e4103-4cce-4536-83fa-4a5040674ad6}|解码|所有解码组件都应都实现此类别。|  
|CATID_DisassemblingParser {9d0e4105-4cce-4536-83fa-4a5040674ad6}|反汇编|所有拆装组件和解析组件应实现此类别。|  
|CATID_Validate {9d0e410d-4cce-4536-83fa-4a5040674ad6}|验证|验证组件应实现此类别。|  
|CATID_PartyResolver {9d0e410e-4cce-4536-83fa-4a5040674ad6}|ResolveParty|用于参与方解析组件的阶段。|  
|CATID_Encoder {9d0e4108-4cce-4536-83fa-4a5040674ad6}|编码|所有编码组件应实现此类别。|  
|CATID_AssemblingSerializer {9d0e4107-4cce-4536-83fa-4a5040674ad6}|序列化|所有序列化和组装组件应实现此类别。|  
|CATID_Any {9d0e4101-4cce-4536-83fa-4a5040674ad6}|这些阶段的任何|如果某管道组件实现此类别，则意味着该组件可置于任何阶段的管道。|  
  
## <a name="see-also"></a>请参阅  
 [使用管道设计器创建管道](../core/creating-pipelines-using-pipeline-designer.md)   
 [关于管道、阶段和组件](../core/about-pipelines-stages-and-components.md)