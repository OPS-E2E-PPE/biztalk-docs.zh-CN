---
title: "TransmitPipeline （接收端口节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TransmitPipeline node [binding file]
ms.assetid: 0f3b728f-1e4a-40e5-9ca9-f7dcdf995cbe
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf1b105f2e7cfc5601469ac55cac6af22aa21a16
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="transmitpipeline-receiveport-node"></a>TransmitPipeline（ReceivePort 节点）
绑定文件的 ReceivePort 节点的 TransmitPipeline 节点提供有关绑定到通过绑定文件导出的双向接收端口的发送管道的特定信息。  
  
> [!NOTE]
>  在接收位置级别绑定由于发送管道的双向接收[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]，此节点为了向后与 BizTalk Server 2004 的兼容性。 发送管道的双向接收绑定在 BizTalk Server 2004 中的接收端口级别。 为此节点已从 BizTalk Server 2004 导出绑定文件将应用于引用每个双向接收位置的发送管道节点时设置的接收端口导入到绑定文件的属性[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]。  
  
## <a name="nodes-in-the-transmitpipeline-node"></a>TransmitPipeline 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Name|Attribute|xs:string|指定发送管道的名称。|可选|默认值：空|  
|FullyQualifiedName|Attribute|xs:string|指定管道的完全限定名，包括程序集的名称（此管道是作为该程序集的一部分部署的）。|可选|默认值：空|  
|类型|Attribute|xs:int|指定管道的类型。|Required|默认值：无<br /><br /> 可能的值记录在<br /><br /> [Microsoft.BizTalk.ExplorerOM.PipelineType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetype.aspx)枚举。|  
|TrackingOption|Attribute|PipelineTrackingTypes (SimpleType)|指定管道的跟踪选项。|Required|默认值：无<br /><br /> 可能的值记录在 [Microsoft.BizTalk.ExplorerOM.PipelineTrackingTypes](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetrackingtypes.aspx) 枚举中。|  
|说明|Attribute|xs:string|指定发送管道的说明。|可选|默认值：空|  
  
## <a name="see-also"></a>另请参阅  
 [发送管道](../core/sendpipeline-receivelocation-node.md)   
 [接收位置](../core/receivelocation-receivelocations-node.md)