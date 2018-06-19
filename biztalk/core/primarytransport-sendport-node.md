---
title: PrimaryTransport （发送端口节点） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- PrimaryTransport node [binding file]
ms.assetid: 22b68d27-f280-4272-84b8-8a50f230228a
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b2d60f3b7fbb09e2e106a4d91f1eca0385aa155
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264933"
---
# <a name="primarytransport-sendport-node"></a>PrimaryTransport（“发送端口”节点）
绑定文件的“发送端口”节点的“PrimaryTransport”节点提供了有关主传输（它绑定到与绑定文件一起导出的发送端口）的特定信息。  
  
## <a name="nodes-in-the-primarytransport-node"></a>“PrimaryTransport”节点中的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**Description**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Address|元素|xs:string|指定传输地址（或 URI）。|可选|默认值：空|  
|[TransportType （PrimaryTransport 节点）](../core/transporttype-primarytransport-node.md)|录制|ProtocolType (ComplexType)|指定传输类型，同时也是用于此传输的适配器的名称。|可选|默认值：无|  
|TransportTypeData|元素|xs:string|指定特定于适配器的配置信息。|可选|默认值：空<br /><br /> 请参阅[集成 BizTalk 适配器的配置属性](../core/configuration-properties-for-integrated-biztalk-adapters.md)适配器可以存储在此字符串的属性有关的特定信息。|  
|RetryCount|元素|xs:int|指定用于传输的适配器的重试次数。|必需|默认值：无|  
|RetryInterval|元素|xs:int|指定用于传输的适配器的重试间隔，以分钟为单位。|必需|默认值：无|  
|ServiceWindowEnabled|元素|xs:boolean|指定是否为用于传输的适配器启用服务时段。|必需|默认值：无<br /><br /> 设置为**true**如果启用了服务时段，否则设置为**false**。|  
|FromTime|元素|xs:dateTime|指定服务时段的开始时间。|必需|默认值：无|  
|ToTime|元素|xs:dateTime|指定的服务时段的结束时间。|必需|默认值：无|  
|主|元素|xs:boolean|指定用于传输的适配器是否为主适配器。|必需|默认值：无<br /><br /> 设置为**true**如果主与传输一起使用的适配器，否则设置为**false**。|  
|OrderedDelivery|元素|xs:boolean|指定用于传输的适配器是否应按顺序发送消息。|必需|默认值：无<br /><br /> 设置为**true**如果传输为以按顺序发送消息，否则设置为**false**。|  
|DeliveryNotification|元素|xs:int|指定用于传输的适配器是否应返回送达通知以便指示传输已成功。|必需|默认值：无<br /><br /> 设置为**true**传递通知，否则设置为**false**。|  
|[发送处理程序](../core/sendhandler-primarytransport-node.md)|录制|SendHandlerRef (ComplexType)|指定的发送处理程序与传输一起使用的适配器。|必需|默认值：无|