---
title: SendPortRef （发送端口节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SendPortRef node [binding file]
ms.assetid: 6c799b23-a9a4-4686-a04e-0450b4eef889
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9290a535ebcaf0c23097cacbd3412f64c2808f40
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22269957"
---
# <a name="sendportref-sendports-node"></a>SendPortRef（“发送端口”节点）
绑定文件的 SendPorts 节点的 SendPortRef 节点可指定分发列表所引用的发送端口的名称。  
  
> [!NOTE]
>  分发列表指 BizTalk 管理员中的发送端口组。  
  
## <a name="nodes-in-the-sendportref-node"></a>SendPortRef 节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Name|Attribute|xs:string|指定分发列表引用的发送端口的名称。|可选|默认值：空|