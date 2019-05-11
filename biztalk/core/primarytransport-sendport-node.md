---
title: PrimaryTransport （SendPort 节点） |Microsoft Docs
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
ms.openlocfilehash: 5b1b42eae58a5207e56e8c713c4a84603a166640
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65299887"
---
# <a name="primarytransport-sendport-node"></a>PrimaryTransport （SendPort 节点）
绑定文件的发送端口节点的 PrimaryTransport 节点提供有关绑定到与绑定文件一起导出的发送端口的主传输的特定信息。  
  
## <a name="nodes-in-the-primarytransport-node"></a>中的 PrimaryTransport 节点的节点  
 下表列出了可为绑定文件的此节点设置的属性：  
  
|**名称**|**节点类型**|**数据类型**|**说明**|**限制**|**注释**|  
|--------------|-------------------|-------------------|---------------------|----------------------|------------------|  
|Address|元素|xs:string|指定的传输地址 （或 URI）。|可选|默认值：空|  
|[TransportType（“PrimaryTransport”节点）](../core/transporttype-primarytransport-node.md)|录制|ProtocolType (ComplexType)|指定传输类型，也是使用为此传输的适配器的名称。|可选|默认值：无|  
|TransportTypeData|元素|xs:string|指定特定于适配器的配置信息。|可选|默认值：空<br /><br /> 请参阅[集成的 BizTalk 适配器的配置属性](../core/configuration-properties-for-integrated-biztalk-adapters.md)适配器可以存储在此字符串中的属性有关的特定信息。|  
|RetryCount|元素|xs:int|指定用于传输的适配器的重试次数。|Required|默认值：无|  
|RetryInterval|元素|xs:int|指定用于传输的适配器的几分钟内重试时间间隔。|Required|默认值：无|  
|ServiceWindowEnabled|元素|xs:boolean|指定是否为用于传输的适配器启用服务时段。|Required|默认值：无<br /><br /> 设置为 **，则返回 true**如果已启用服务时段，否则设置为**false**。|  
|FromTime|元素|xs:dateTime|指定服务时段的开始时间。|Required|默认值：无|  
|ToTime|元素|xs:dateTime|指定服务时段的结束时间。|Required|默认值：无|  
|基本|元素|xs:boolean|指定用于传输的适配器是否为主。|Required|默认值：无<br /><br /> 设置为 **，则返回 true**如果主要用于传输的适配器，否则设置为**false**。|  
|OrderedDelivery|元素|xs:boolean|指定用于传输的适配器应按顺序发送消息。|Required|默认值：无<br /><br /> 设置为 **，则返回 true**如果传输是按顺序发送消息，否则设置为**false**。|  
|DeliveryNotification|元素|xs:int|指定用于传输的适配器应返回送达通知以便指示传输是否成功。|Required|默认值：无<br /><br /> 设置为 **，则返回 true**送达通知，否则设置为**false**。|  
|[SendHandler](../core/sendhandler-primarytransport-node.md)|录制|SendHandlerRef (ComplexType)|指定用于传输的适配器的发送处理程序。|Required|默认值：无|