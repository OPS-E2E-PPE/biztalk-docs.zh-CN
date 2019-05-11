---
title: 接收位置传输类型 （ReceiveLocation 节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ReceiveLocationTransportType node [binding file]
ms.assetid: 375076c3-d5e6-4c25-b054-b452e29717e0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aba0abcf71824d1109bb7a47104ab928df247fd0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398134"
---
# <a name="receivelocationtransporttype-receivelocation-node"></a>接收位置传输类型 （ReceiveLocation 节点）
绑定文件的 ReceiveLocation 节点的接收位置传输类型节点包含有关与绑定文件一起导出的传输相关联的适配器的特定信息。  
  
## <a name="nodes-in-the-receivelocationtransporttype-node"></a>节点中的接收位置传输类型节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|“属性”|特性|xs:string|指定与此传输关联的适配器的名称。|可选|默认值：空|  
|功能|特性|xs:int|指定与此传输关联的适配器的功能。|Required|默认值：无<br /><br /> 可能的值包括 [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) 枚举中的值。|  
|ConfigurationClsid|特性|xs:string|指定与此传输关联的适配器的配置 GUID。|可选|默认值：空|