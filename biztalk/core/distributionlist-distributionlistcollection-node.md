---
title: DistributionList （DistributionListCollection 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- DistributionList node [binding file]
ms.assetid: 51864a5c-1697-4804-ac18-8211494f3ff0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 732ffa00a2147212e688e9add579044c570faf6c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65350832"
---
# <a name="distributionlist-distributionlistcollection-node"></a>DistributionList （DistributionListCollection 节点）
绑定文件的 DistributionList 节点包含有关与绑定文件一起导出的通讯组列表的特定信息。 通讯组列表称为发送端口组在 BizTalk Server 管理器。  
  
## <a name="nodes-in-the-distributionlist-node"></a>DistributionList 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|“属性”|特性|xs:string|指定分发列表的名称。|可选|默认值：空|  
|[SendPorts](../core/sendports-distributionlist-node.md)|录制|ArrayOfSendPortRef (ComplexType)|指定发送端口或通讯组列表中包含的发送端口。|可选|默认值：无|  
|“筛选器”|元素|xs:string|指定使用此分发列表的可选筛选器表达式的名称。|Required|默认值：空|  
|ApplicationName|元素|xs:string|指定分发列表与之关联的应用程序的名称。|Required|默认值：空|  
|Description|元素|xs:string|指定分发列表的说明。|Required|默认值：空|