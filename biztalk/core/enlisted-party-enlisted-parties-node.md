---
title: 已登记参与方 （已登记参与方节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Enlisted Parties node [binding file]
ms.assetid: 2ff7b563-17c5-48e9-b33e-62c821188448
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 034cc538bb358f887cda761bb0cf6a0d9d1116e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389080"
---
# <a name="enlisted-party-enlisted-parties-node"></a>已登记参与方 （已登记参与方节点）
绑定文件的已登记参与方节点包含有关与绑定文件一起导出的角色相关联的已登记参与方的特定信息。  
  
## <a name="nodes-in-the-enlisted-party-node"></a>在已登记参与方节点的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|“属性”|特性|xs:string|指定已登记参与方的名称|可选|默认值：空|  
|[映射](../core/mappings-enlisted-party-node.md)|录制|ArrayOfEnlistedPartyMapping (ComplexType)|参与方端口和角色端口类型操作之间的映射的容器节点。|可选|默认值：无|