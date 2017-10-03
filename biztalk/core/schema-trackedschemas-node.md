---
title: "架构 （TrackedSchemas 节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Schema node
ms.assetid: a503aad6-07f8-4650-a214-4d2f6650cb80
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5376c505332ed05507169c1db2dc54ec4e7bdfe6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="schema-trackedschemas-node"></a>架构（TrackedSchemas 节点）
绑定文件的“TrackedSchemas”节点的 Schema 节点描述了绑定到与绑定文件一起导出的服务的架构。  
  
## <a name="nodes-in-the-schema-node"></a>Schema 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|FullName|Attribute|xs:string|指定架构的全名。|可选|默认值：空|  
|AssemblyQualifiedName|Attribute|xs:string|指定包含此架构的程序集的限定名。|可选|默认值：空|  
|AlwaysTrackAllProperties|Attribute|xs:boolean|指定是否跟踪指定程序集的所有属性。|必需|默认值：无<br /><br /> 设置为**true**若要跟踪的所有属性，否则设置为**false**。|  
|Description|Attribute|xs:string|为架构指定描述。|可选|默认值：空|  
|[TrackedPropertyNames （架构节点）](../core/trackedpropertynames-schema-node.md)|录制|ArrayOfString (ComplexType)|指定要跟踪的属性的元素的容器。|可选|默认值：无|