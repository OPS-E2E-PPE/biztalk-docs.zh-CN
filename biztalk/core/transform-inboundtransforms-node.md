---
title: 转换 （InboundTransforms 节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Transform node [binding file]
ms.assetid: c1bad23e-78a4-4fd4-95ef-30601393d53c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 705b1b04b8305330ab1d5ff705c5025f24b0685c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="transform-inboundtransforms-node"></a>Transform（InboundTransforms 节点）
绑定文件的 InboundTransforms 节点的 Transform 节点包含与该绑定文件一起导出的 BizTalk Server 映射有关的信息。  
  
## <a name="nodes-in-the-transform-node"></a>Transform 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|FullName|Attribute|xs:string|指定映射的全名。|可选|默认值：空|  
|AssemblyQualifiedName|Attribute|xs:string|指定映射的程序集限定名。|可选|默认值：空|