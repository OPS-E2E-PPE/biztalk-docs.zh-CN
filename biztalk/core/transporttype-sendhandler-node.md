---
title: TransportType （SendHandler 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- TransportType node [binding file]
ms.assetid: ee87a409-33dd-4111-ba6a-ead3bacc80aa
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bd31acc6cd31e359c1fc448d3468918675553d84
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65401856"
---
# <a name="transporttype-sendhandler-node"></a>TransportType （SendHandler 节点）
绑定文件的 SendHandler 节点的 TransportType 节点包含有关指定适配器的特定信息，该适配器是与随绑定文件一起导出的发送处理程序关联的适配器。  
  
## <a name="nodes-in-the-transporttype-node"></a>TransportType 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|“属性”|特性|xs:string|指定与发送处理程序相关联的适配器的名称。|可选|默认值：空|  
|功能|特性|xs:int|指定与发送处理程序相关联的适配器的功能。|Required|默认值：无<br /><br /> 可能的值包括 [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) 枚举中的值。|  
|ConfigurationClsid|特性|xs:string|指定与发送处理程序相关联的适配器的配置 GUID。|可选|默认值：空|