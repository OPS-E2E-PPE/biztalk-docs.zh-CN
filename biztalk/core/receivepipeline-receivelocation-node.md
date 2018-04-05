---
title: ReceivePipeline （接收位置节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ReceivePipeline node [binding file]
ms.assetid: bd90ca2d-21e4-4d21-bc67-f16a150053e4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 122ffcfe7fe2d2cfc49b51c98b7251a19f5a0e31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receivepipeline-receivelocation-node"></a>ReceivePipeline（“接收位置”节点）
绑定文件的“发送端口”节点的 ReceiveLocation 节点包含有关用于接收位置的接收管道的特定信息，该接收位置与绑定文件一起导出。  
  
## <a name="nodes-in-the-receivepipeline-node"></a>ReceivePipeline 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Name|Attribute|xs:string|指定接收管道的名称。|可选|默认值：空|  
|FullyQualifiedName|Attribute|xs:string|指定管道的完全限定名，其中包括程序集（管道作为该程序集的一部分部署）的名称。|可选|默认值：空|  
|类型|Attribute|xs:int|指定管道的类型。|Required|默认值：无<br /><br /> 可能的值记录在<br /><br /> [Microsoft.BizTalk.ExplorerOM.PipelineType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetype.aspx)枚举。|  
|TrackingOption|Attribute|PipelineTrackingTypes (SimpleType)|指定管道的跟踪选项。|Required|默认值：无<br /><br /> 可能的值记录在 [Microsoft.BizTalk.ExplorerOM.PipelineTrackingTypes](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetrackingtypes.aspx) 枚举中。|  
|说明|Attribute|xs:string|指定接收管道的说明。|不需要|默认值：空|