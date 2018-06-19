---
title: 主机 （服务节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Host node [binding file]
ms.assetid: 597522db-0336-43b1-b464-d17cffbf25be
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9c70c23105a8d2f2ebe389b22ddf910b4166994
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246557"
---
# <a name="host-service-node"></a>主机 （服务节点）
绑定文件的服务节点的主机节点描述与使用绑定文件导出的服务关联的主机。  
  
## <a name="nodes-in-the-host-node"></a>在主机节点的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Name|Attribute|xs:string|指定的主机的名称。|可选|默认值：空|  
|NTGroupName|Attribute|xs:string|指定与主机关联的 Windows NT 组名称。|可选|默认值：空|  
|类型|Attribute|xs:int|指定的主机类型，如下所示进程或隔离。|必需|默认值：无<br /><br /> 可能的值中所述[Microsoft.BizTalk.ExplorerOM.HostType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.hosttype.aspx)枚举。|  
|受信任|Attribute|xs:boolean|指定 BizTalk 主机是否可以信任要收集的身份验证信息。|必需|默认值：无<br /><br /> 设置为**true**如果主机是受信任，否则设置为**false**。|