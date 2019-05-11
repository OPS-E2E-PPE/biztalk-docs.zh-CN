---
title: TransmitPipeline （ReceivePort 节点） |Microsoft Docs
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
ms.openlocfilehash: b134d615aecac2eafc21ada63f3caa50664ca2e0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243200"
---
# <a name="transmitpipeline-receiveport-node"></a>TransmitPipeline （ReceivePort 节点）
ReceivePort 节点的绑定文件提供了有关绑定到双向发送管道的特定信息的 TransmitPipeline 节点接收端口与绑定文件一起导出。  
  
> [!NOTE]
>  发送管道双向接收绑定在 BizTalk Server 中的接收位置级别，因为此节点被用于向后与 BizTalk Server 2004 的兼容性。 发送管道双向接收绑定在 BizTalk Server 2004 中的接收端口级别。 从 BizTalk Server 2004 导出的绑定文件的此节点设置的属性将应用于所引用接收端口绑定文件导入到 BizTalk Server 时每个双向接收位置的 SendPipeline 节点。  
  
## <a name="nodes-in-the-transmitpipeline-node"></a>TransmitPipeline 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|“属性”|特性|xs:string|指定发送管道的名称。|可选|默认值：空|  
|FullyQualifiedName|特性|xs:string|指定管道，其中包括的管道已部署的一部分的程序集名称的完全限定的的名称。|可选|默认值：空|  
|类型|特性|xs:int|指定管道的类型。|Required|默认值：无<br /><br /> 可能的值记录在<br /><br /> [Microsoft.BizTalk.ExplorerOM.PipelineType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetype.aspx)枚举。|  
|TrackingOption|特性|PipelineTrackingTypes (SimpleType)|指定管道的跟踪选项。|Required|默认值：无<br /><br /> 可能的值记录在 [Microsoft.BizTalk.ExplorerOM.PipelineTrackingTypes](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetrackingtypes.aspx) 枚举中。|  
|Description|特性|xs:string|指定发送管道的说明。|可选|默认值：空|  
  
## <a name="see-also"></a>请参阅  
 [SendPipeline](../core/sendpipeline-receivelocation-node.md)   
 [ReceiveLocation](../core/receivelocation-receivelocations-node.md)