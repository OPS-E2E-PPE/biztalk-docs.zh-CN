---
title: 架构 （TrackedSchemas 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Schema node
ms.assetid: a503aad6-07f8-4650-a214-4d2f6650cb80
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe27ed2ce631fe27cb34ec44bb792349737dbe01
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396883"
---
# <a name="schema-trackedschemas-node"></a>架构 （TrackedSchemas 节点）
绑定文件的 TrackedSchemas 节点的架构节点描述了绑定到与绑定文件一起导出的服务的架构。  
  
## <a name="nodes-in-the-schema-node"></a>节点中的架构节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|FullName|特性|xs:string|指定架构的完整名称。|可选|默认值：空|  
|AssemblyQualifiedName|特性|xs:string|指定包含此架构的程序集的完全限定的名称。|可选|默认值：空|  
|AlwaysTrackAllProperties|特性|xs:boolean|指定是否为指定的程序集跟踪所有属性。|Required|默认值：无<br /><br /> 设置为 **，则返回 true**若要跟踪的所有属性，否则设置为**false**。|  
|Description|特性|xs:string|指定架构的说明。|可选|默认值：空|  
|[TrackedPropertyNames（Schema 节点）](../core/trackedpropertynames-schema-node.md)|录制|ArrayOfString (ComplexType)|指定要跟踪的属性的元素的容器。|可选|默认值：无|