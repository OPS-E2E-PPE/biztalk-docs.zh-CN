---
title: TransmitPipeline （SendPort 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TransmitPipeline node [binding file]
ms.assetid: cee55451-6c3f-4e37-aef9-870d4b5d23aa
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4985117385195447a1f4dc45586e0c04da5b3da
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243073"
---
# <a name="transmitpipeline-sendport-node"></a>TransmitPipeline （SendPort 节点）
绑定文件的“发送端口”节点的 TransmitPipeline 节点提供有关与随绑定文件导出的发送端口绑定的发送管道的特定信息。  
  
## <a name="nodes-in-the-transmitpipeline-node"></a>TransmitPipeline 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|“属性”|特性|xs:string|指定发送管道的名称。|可选|默认值：空|  
|FullyQualifiedName|特性|xs:string|指定管道的完全限定名，其中包括程序集（管道作为该程序集的一部分部署）的名称。|可选|默认值：空|  
|类型|特性|xs:int|指定管道的类型。|Required|默认值：无<br /><br /> 可能的值记录在 [Microsoft.BizTalk.ExplorerOM.PipelineType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetype.aspx) 枚举中。|  
|TrackingOption|特性|PipelineTrackingTypes (SimpleType)|指定管道的跟踪选项。|Required|默认值：无<br /><br /> 可能的值记录在 [Microsoft.BizTalk.ExplorerOM.PipelineTrackingTypes](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetrackingtypes.aspx) 枚举中。|  
|Description|特性|xs:string|指定发送管道的说明。|可选|默认值：空|