---
title: "转换 （转换节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Transform node [binding file]
ms.assetid: 2d1387f1-1668-4982-a717-52478e2a91f9
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33e70e5a2bcba2925941e727034b90c9fe4b1418
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="transform-transforms-node"></a>Transform（Transforms 节点）
绑定文件的“转换”节点下的“转换”节点包含有关随同该绑定文件一起导出的 BizTalk Server 映射的特定信息。  
  
## <a name="nodes-in-the-transform-node"></a>Transform 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|FullName|Attribute|xs:string|指定映射的全名。|可选|默认值：空|  
|AssemblyQualifiedName|Attribute|xs:string|指定映射的程序集限定名。|可选|默认值：空|