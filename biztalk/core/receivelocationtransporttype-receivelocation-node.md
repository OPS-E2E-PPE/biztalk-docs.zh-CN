---
title: ReceiveLocationTransportType （接收位置节点） |Microsoft 文档
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
ms.openlocfilehash: d0eae3e2c4fd9f5f668cb12ffd630640b1b63c74
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268717"
---
# <a name="receivelocationtransporttype-receivelocation-node"></a>ReceiveLocationTransportType（“接收位置”节点）
绑定文件的“接收位置”节点的“接收位置传输类型”节点包含有关适配器的特定信息，该适配器与随同该绑定文件一起导出的传输相关联。  
  
## <a name="nodes-in-the-receivelocationtransporttype-node"></a>“接收位置传输类型”节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Name|Attribute|xs:string|指定与此传输关联的适配器的名称。|可选|默认值：空|  
|功能|Attribute|xs:int|指定与此传输关联的适配器的功能。|Required|默认值：无<br /><br /> 可能的值包括 [Microsoft.BizTalk.ExplorerOM.Capabilities](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.capabilities.aspx) 枚举中的值。|  
|ConfigurationClsid|Attribute|xs:string|指定与此传输关联的适配器的配置 GUID。|可选|默认值：空|