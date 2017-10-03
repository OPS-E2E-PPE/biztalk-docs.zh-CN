---
title: "端口 （端口节点） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Port node [binding file]
ms.assetid: 6c9a3e5f-0b3c-40f8-9a8d-5a83bd559021
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 01a808f4415019ba48deb1b3b80ad8aae9e1db04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="port-ports-node"></a>端口 （端口节点）
绑定文件的端口节点包含与绑定到随该绑定文件一起导出的服务的端口或分发列表有关的特定信息。  
  
> [!NOTE]
>  分发列表指 BizTalk Server 管理控制台中的发送端口组。  
  
## <a name="nodes-in-the-port-node"></a>端口节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Name|Attribute|xs:string|指定端口的名称。|可选|默认值：空|  
|修饰符|Attribute|xs:int|指定端口的类型修饰符。|必需|默认值：无<br /><br /> 可能的值包括在提供的那些[Microsoft.BizTalk.ExplorerOM.PortModifier](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.portmodifier.aspx)枚举。|  
|BindingOption|Attribute|xs:int|定义端口的绑定类型。|必需|默认值：无<br /><br /> 可能的值包括在提供的那些[Microsoft.BizTalk.ExplorerOM.BindingType](http://msdn.microsoft.com/library/microsoft.biztalk.explorerom.bindingtype.aspx)枚举。|  
|[SendPortRef](../core/sendportref-port-node.md)|录制|SendPortRef (ComplexType)|某服务引用的发送端口的容器节点。|可选|默认值：空|  
|[DistributionListRef](../core/distributionlistref-port-node.md)|录制|DistributionListRef (ComplexType)|某服务引用的分发列表的容器节点。|可选|默认值：空|  
|[ReceivePortRef](../core/receiveportref-port-node.md)|录制|ReceivePortRef (ComplexType)|某服务引用的接收端口的容器节点。|可选|默认值：空|