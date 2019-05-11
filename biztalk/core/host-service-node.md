---
title: 主机 （服务节点） |Microsoft Docs
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
ms.openlocfilehash: 3a408b8f1bd269ff45881b31cd8a75d26bbc89a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387520"
---
# <a name="host-service-node"></a>主机 （服务节点）
绑定文件的服务节点的主机节点描述了与绑定文件一起导出的服务关联的主机。  
  
## <a name="nodes-in-the-host-node"></a>节点中的主机节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|“属性”|特性|xs:string|指定的主机的名称。|可选|默认值：空|  
|NTGroupName|特性|xs:string|指定与主机关联的 Windows NT 组名称。|可选|默认值：空|  
|类型|特性|xs:int|指定进程或独立的主机类型。|Required|默认值：无<br /><br /> 可能的值所述[Microsoft.BizTalk.ExplorerOM.HostType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.hosttype.aspx)枚举。|  
|受信任|特性|xs:boolean|指定的 BizTalk 主机是否可信任，以收集身份验证信息。|Required|默认值：无<br /><br /> 设置为 **，则返回 true**如果主机是受信任，否则设置为**false**。|