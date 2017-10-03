---
title: "登记方 （登记的方节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Enlisted Parties node [binding file]
ms.assetid: 2ff7b563-17c5-48e9-b33e-62c821188448
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 624f74d3b49b80e8000723c3f7451c52b37c8d3d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="enlisted-party-enlisted-parties-node"></a>已登记参与方（“已登记参与方”节点）
绑定文件的“已登记参与方”节点包含有关已登记参与方的特定信息，该已登记参与方与随同该绑定文件一起导出的角色相关联。  
  
## <a name="nodes-in-the-enlisted-party-node"></a>登记方节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Name|Attribute|xs:string|指定已登记参与方的名称。|可选|默认值：空|  
|[映射](../core/mappings-enlisted-party-node.md)|录制|ArrayOfEnlistedPartyMapping (ComplexType)|用于参与方端口和角色端口类型操作之间的映射的容器节点。|可选|默认值：无|