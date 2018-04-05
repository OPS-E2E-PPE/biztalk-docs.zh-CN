---
title: 角色 （服务节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Roles node [binding file]
ms.assetid: 847755c9-1697-41a0-b870-f9e795a1a2a6
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b47f5ae94326b0555c0c9cd84752cb9f1c409daa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="roles-service-node"></a>角色 （服务节点）
对于任何“角色”节点，只要它提供与绑定到随某个绑定文件导出的服务的每个角色有关的特定信息，则该绑定文件的“角色”节点就是此节点的父节点。  
  
## <a name="nodes-in-the-roles-node"></a>“角色”节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[角色](../core/role-roles-node.md)|录制|RoleRef (ComplexType)|指定与绑定到随绑定文件导出的服务的角色有关的信息。|可选|默认值：无|