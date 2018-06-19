---
title: TransmitPipeline （接收端口节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TransmitPipeline node [binding file]
ms.assetid: 0f3b728f-1e4a-40e5-9ca9-f7dcdf995cbe
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64b17179b7131839dc369e9bdecf5e40dd831e4d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26009022"
---
# <a name="transmitpipeline-receiveport-node"></a>TransmitPipeline（ReceivePort 节点）
绑定文件的 ReceivePort 节点的 TransmitPipeline 节点提供有关绑定到通过绑定文件导出的双向接收端口的发送管道的特定信息。  
  
> [!NOTE]
>  发送管道的双向接收绑定在 BizTalk Server 中的接收位置级别，因为此节点被为了向后与 BizTalk Server 2004 的兼容性。 发送管道的双向接收绑定在 BizTalk Server 2004 中的接收端口级别。 为绑定文件已从 BizTalk Server 2004 导出的此节点设置的属性将应用到发送管道时绑定文件导入到 BizTalk Server 接收端口通过引用每个双向接收位置的节点。  
  
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
 [ReceiveLocation](../core/receivelocation-receivelocations-node.md)