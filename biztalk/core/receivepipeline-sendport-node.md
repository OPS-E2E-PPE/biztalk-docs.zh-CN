---
title: "ReceivePipeline （发送端口节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: ReceivePipeline node [binding file]
ms.assetid: 5305f255-e7a2-4052-bf50-4fb207cfae8d
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 210c54b18cc174f31ff795a657f7d23044cebc58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="receivepipeline-sendport-node"></a>ReceivePipeline （发送端口节点）
绑定文件的“发送端口”节点的 ReceivePipeline 节点包含有关绑定到双向发送端口的接收管道的特定信息，该双向发送端口与绑定文件一起导出。  
  
## <a name="nodes-in-the-receivepipeline-node"></a>ReceivePipeline 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Name|Attribute|xs:string|指定发送管道的名称。|可选|默认值：空|  
|FullyQualifiedName|Attribute|xs:string|指定管道的完全限定名，包括程序集的名称（此管道是作为该程序集的一部分部署的）。|可选|默认值：空|  
|类型|Attribute|xs:int|指定管道的类型。|Required|默认值：无<br /><br /> 可能的值记录在<br /><br /> [Microsoft.BizTalk.ExplorerOM.PipelineType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetype.aspx)枚举。|  
|TrackingOption|Attribute|PipelineTrackingTypes (SimpleType)|指定管道的跟踪选项。|Required|默认值：无<br /><br /> 可能的值记录在 [Microsoft.BizTalk.ExplorerOM.PipelineTrackingTypes](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetrackingtypes.aspx) 枚举中。|  
|说明|Attribute|xs:string|指定发送管道的说明。|可选|默认值：空|