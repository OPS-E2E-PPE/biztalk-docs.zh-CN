---
title: 角色 （角色节点） |Microsoft Docs
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
ms.openlocfilehash: 652702d35eb0ab1f9fd974491e5ae94e2a1cec4f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254704"
---
# <a name="role-roles-node"></a>角色 （角色节点）
绑定文件的角色节点的角色节点指定绑定到与绑定文件一起导出的服务的角色有关的信息。  
  
## <a name="nodes-in-the-role-node"></a>节点中的角色节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|“属性”|特性|xs:string|指定的角色的名称。|可选|默认值：空|  
|RoleLinkTypeName|特性|xs:string|指定与角色关联的角色链接类型的名称|可选|默认值：空|  
|RoleType|特性|RoleRefType (SimpleType)|指定与角色关联的角色类型。|Required|默认值：无<br /><br /> 可能的值包括：<br /><br /> -未知<br />实现<br />-使用|  
|[已登记参与方](../core/enlisted-parties-role-node.md)|录制|ArrayOfEnlistedParty (ComplexType)|已登记的参与方绑定到此角色的容器节点。|可选|默认值：无|