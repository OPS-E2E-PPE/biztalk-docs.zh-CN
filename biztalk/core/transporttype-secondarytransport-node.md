---
title: "TransportType （SecondaryTransport 节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: TransportType node [binding file]
ms.assetid: ed66c7ef-32b6-4110-b932-f96a45a29618
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7bb0b9460e6c4689dab169a37a9d6b6c51753598
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="transporttype-secondarytransport-node"></a>TransportType （SecondaryTransport 节点）
绑定文件的“SecondaryTransport”节点的“TransportType”节点包含有关适配器的特定信息，该适配器与随同该绑定文件一起导出的传输相关联。  
  
## <a name="nodes-in-the-transporttype-node"></a>TransportType 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Name|Attribute|xs:string|指定与此传输关联的适配器的名称。|可选|默认值：空|  
|功能|Attribute|xs:int|指定与此传输关联的适配器的功能。|Required|默认值：无<br /><br /> 可能的值包括 [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) 枚举中的值。|  
|ConfigurationClsid|Attribute|xs:string|指定与此传输关联的适配器的配置 GUID。|可选|默认值：空|