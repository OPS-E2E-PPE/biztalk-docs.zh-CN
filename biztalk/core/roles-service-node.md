---
title: 角色 （服务节点） |Microsoft Docs
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
ms.openlocfilehash: 2ff156bce1fa4114aac34641ce52d28cdf182ecd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65240406"
---
# <a name="roles-service-node"></a>角色 （服务节点）
绑定文件的角色节点是所有角色节点，提供有关绑定到与绑定文件一起导出的服务的每个角色的特定信息的父节点。  
  
## <a name="nodes-in-the-roles-node"></a>在角色节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|[角色](../core/role-roles-node.md)|录制|RoleRef (ComplexType)|指定有关绑定到与绑定文件一起导出的服务角色信息。|可选|默认值：无|