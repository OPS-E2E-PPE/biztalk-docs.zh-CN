---
title: 角色 （角色节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Role node [binding file]
ms.assetid: dfe2a579-7090-4d85-87e5-d627598c4ee8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d70e99568db262ef5abd5b0885cb814c722347f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="role-roles-node"></a>角色（“角色”节点）
绑定文件的“角色”节点的“角色”节点指定了与绑定到随绑定文件一起导出的服务的角色有关的信息。  
  
## <a name="nodes-in-the-role-node"></a>在角色节点的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Name|Attribute|xs:string|指定角色的名称。|可选|默认值：空|  
|RoleLinkTypeName|Attribute|xs:string|指定与角色相关联的角色链接类型的名称|可选|默认值：空|  
|RoleType|Attribute|RoleRefType (SimpleType)|指定与角色相关联的角色类型。|必需|默认值：无<br /><br /> 可能的值包括：<br /><br /> -未知<br />实现<br />-使用|  
|[已登记参与方](../core/enlisted-parties-role-node.md)|录制|ArrayOfEnlistedParty (ComplexType)|绑定到此角色的已登记参与方的容器节点。|可选|默认值：无|