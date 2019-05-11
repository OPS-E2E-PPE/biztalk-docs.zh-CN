---
title: 端口 （端口节点） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Port node [binding file]
ms.assetid: 6c9a3e5f-0b3c-40f8-9a8d-5a83bd559021
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29660dbdc066557d2036e53c12e1ad278eb9c225
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394874"
---
# <a name="port-ports-node"></a>端口 （端口节点）
绑定文件的端口节点包含有关绑定到与绑定文件一起导出的服务的端口或通讯组列表的特定信息。  
  
> [!NOTE]
>  通讯组列表称为 BizTalk Server 管理控制台中的发送端口组。  
  
## <a name="nodes-in-the-port-node"></a>在端口节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|“属性”|特性|xs:string|指定的端口的名称。|可选|默认值：空|  
|修饰符|特性|xs:int|指定该端口的类型修饰符。|Required|默认值：无<br /><br /> 可能的值包括可[Microsoft.BizTalk.ExplorerOM.PortModifier](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.portmodifier.aspx)枚举。|  
|BindingOption|特性|xs:int|定义端口的绑定的类型。|Required|默认值：无<br /><br /> 可能的值包括可[Microsoft.BizTalk.ExplorerOM.BindingType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.bindingtype.aspx)枚举。|  
|[SendPortRef](../core/sendportref-port-node.md)|录制|SendPortRef (ComplexType)|容器节点发送端口的服务引用。|可选|默认值：空|  
|[DistributionListRef](../core/distributionlistref-port-node.md)|录制|DistributionListRef (ComplexType)|某服务引用的分发列表的容器节点。|可选|默认值：空|  
|[ReceivePortRef](../core/receiveportref-port-node.md)|录制|ReceivePortRef (ComplexType)|某服务引用的接收端口的容器节点。|可选|默认值：空|