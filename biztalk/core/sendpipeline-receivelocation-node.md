---
title: 发送管道 （ReceiveLocation 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendPipeline node [binding file]
ms.assetid: 7dcad2f1-b11f-4015-9067-b7ba40ee6cda
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1b6fd5239b63c71350688328b4b60d7a585abc9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398991"
---
# <a name="sendpipeline-receivelocation-node"></a>发送管道 （ReceiveLocation 节点）
绑定文件的 ReceiveLocation 节点的 SendPipeline 节点提供有关绑定到与绑定文件一起导出的接收位置的发送管道的特定信息。  
  
## <a name="nodes-in-the-sendpipeline-node"></a>节点中的 SendPipeline 节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|“属性”|特性|xs:string|指定发送管道的名称。|可选|默认值：空|  
|FullyQualifiedName|特性|xs:string|指定管道的完全限定名，其中包括程序集（管道作为该程序集的一部分部署）的名称。|可选|默认值：空|  
|类型|特性|xs:int|指定管道的类型。|Required|默认值：无<br /><br /> 可能的值记录在<br /><br /> [Microsoft.BizTalk.ExplorerOM.PipelineType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetype.aspx)枚举。|  
|TrackingOption|特性|PipelineTrackingTypes (SimpleType)|指定管道的跟踪选项。|Required|默认值：无<br /><br /> 可能的值记录在 [Microsoft.BizTalk.ExplorerOM.PipelineTrackingTypes](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.pipelinetrackingtypes.aspx) 枚举中。|  
|Description|特性|xs:string|指定发送管道的说明。|可选|默认值：空|