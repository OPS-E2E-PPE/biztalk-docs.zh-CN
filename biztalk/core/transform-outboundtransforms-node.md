---
title: Transform （OutboundTransforms 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Transform node [binding file]
ms.assetid: 928a93cd-7a26-4148-b1af-dc0bc316f8c1
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 19c2940dd7700f7d3da63d0e9d897429d154d8e8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65302950"
---
# <a name="transform-outboundtransforms-node"></a>Transform （OutboundTransforms 节点）
绑定文件的 OutboundTransforms 节点的 Transform 节点包含随绑定文件一起导出的 BizTalk Server 映射有关的特定信息。  
  
## <a name="nodes-in-the-transform-node"></a>Transform 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|FullName|特性|xs:string|指定的映射的完整名称。|可选|默认值：空|  
|AssemblyQualifiedName|特性|xs:string|指定映射的程序集限定的名称。|可选|默认值：空|