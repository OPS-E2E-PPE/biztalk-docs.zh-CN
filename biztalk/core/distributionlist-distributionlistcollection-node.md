---
title: DistributionList （DistributionListCollection 节点） |Microsoft 文档
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
ms.openlocfilehash: 931443cdca27e5c06767f075298d50ff999545a0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239333"
---
# <a name="distributionlist-distributionlistcollection-node"></a>DistributionList （DistributionListCollection 节点）
绑定文件的 DistributionList 节点包含有关与绑定文件一起导出的分发列表的特定信息。 分发列表指 BizTalk Server Administrator 组中的发送端口组。  
  
## <a name="nodes-in-the-distributionlist-node"></a>DistributionList 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Name|Attribute|xs:string|指定分发列表的名称。|可选|默认值：空|  
|[发送端口](../core/sendports-distributionlist-node.md)|录制|ArrayOfSendPortRef (ComplexType)|指定在分发列表中包括的一个或多个发送端口。|可选|默认值：无|  
|“筛选器”|元素|xs:string|指定此分发列表中使用的可选筛选器表达式的名称。|必需|默认值：空|  
|ApplicationName|元素|xs:string|指定分发列表与之关联的应用程序的名称。|必需|默认值：空|  
|Description|元素|xs:string|指定分发列表的说明。|必需|默认值：空|