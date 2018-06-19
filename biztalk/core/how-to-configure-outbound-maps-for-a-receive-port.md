---
title: 如何配置出站映射接收端口 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- maps, outbound
- configuring, maps
- managing [receive ports], outbound maps
- maps, configuring
- receive ports, configuring
- configuring, receive ports
- receive ports, outbound maps
ms.assetid: 01a864a1-9e8c-4b82-9d03-91be09d556da
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9006f655879bcb5d8fe2c2448c8feba0642c9a5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248509"
---
# <a name="how-to-configure-outbound-maps-for-a-receive-port"></a>如何为接收端口配置出站映射
本主题将介绍如何使用 BizTalk Server 管理控制台为接收端口配置出站映射。 可以将出站映射与请求-响应接收端口一起使用，以将出站消息从一个架构转换到另一个架构；例如，将公司使用的消息转换到合作伙伴使用的架构中。  
  
 可以使用映射对该接收端口发送的响应消息应用 XSL 转换，而无需通过业务流程来处理该消息。 您可以添加出站映射、删除映射或更改现有映射。 可以为接收端口添加多个映射，但每个映射必须仅仅有唯一的源架构。 有关地图背景信息，请参阅[映射](../core/maps.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-configure-outbound-maps-for-a-receive-port"></a>为接收端口配置出站映射  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开要为其配置出站映射的接收端口所属的 BizTalk 组和 BizTalk 应用程序。  
  
3.  展开**接收端口**，右键单击接收端口，请单击**属性**，然后单击**出站映射**。  
  
4.  下表中所述配置出站映射，然后单击**确定**。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**删除**|单击此项可删除所选映射。|  
    |**源文档**|从下拉列表中，选择要与此端口一起使用的源架构。|  
    |**地图**|从下拉列表中，选择要与此端口关联的映射。|  
    |**目标文档**|从下拉列表中，选择要与此端口一起使用的目标架构。|  
  
## <a name="see-also"></a>另请参阅  
 [管理接收端口](../core/managing-receive-ports.md)   
 [管理映射](../core/managing-maps.md)