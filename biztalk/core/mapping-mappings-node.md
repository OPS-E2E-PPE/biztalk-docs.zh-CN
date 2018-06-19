---
title: 映射 （映射节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Mapping node [binding file]
ms.assetid: bc54c476-505c-4020-b7df-1d19f86329aa
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2c62d46e4d5c2b73eee5094ecda0e20c039798a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262517"
---
# <a name="mapping-mappings-node"></a>Mapping（Mappings 节点）
绑定文件的 Mapping 节点描述登记的参与方的参与方端口与角色端口类型操作之间的映射。  
  
## <a name="nodes-in-the-mapping-node"></a>Mapping 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|PortTypeName|Attribute|xs:string|指定端口类型的名称。|可选|默认值：空|  
|operationName|Attribute|xs:string|指定属于此端口类型的操作。|可选|默认值：空|  
|[SendPortRef](../core/sendportref-mapping-node.md)|录制|SendPortRef (ComplexType)|与此映射关联的发送端口列表的容器节点。|可选|默认值：无|