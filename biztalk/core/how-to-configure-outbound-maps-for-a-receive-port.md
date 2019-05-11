---
title: 如何配置出站映射接收端口 |Microsoft Docs
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
ms.openlocfilehash: ee2d18a2a1d0e8d39001a232d909a805a27f4707
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341280"
---
# <a name="how-to-configure-outbound-maps-for-a-receive-port"></a>如何配置出站映射接收端口
本主题介绍如何使用 BizTalk Server 管理控制台配置接收端口的出站映射。 可以使用出站映射与请求-响应接收端口转换到另一个; 的出站消息从一个架构若要将您的公司使用的消息转换为合作伙伴使用的架构的示例。  
  
 使用映射来应用 XSL 转换，而无需通过业务流程处理该消息的接收端口发送的响应消息。 可以添加出站映射、 删除映射，或更改现有映射到另一个。 可以将多个映射添加到接收端口，但每个映射必须具有唯一的源架构。 有关地图的背景信息，请参阅[映射](../core/maps.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-configure-outbound-maps-for-a-receive-port"></a>若要配置接收端口的出站映射  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开 BizTalk 组和 BizTalk 应用程序想要配置接收端口的出站映射。  
  
3. 展开**接收端口**，右键单击该接收端口，单击**属性**，然后单击**出站映射**。  
  
4. 下表中所述配置出站映射，然后单击**确定**。  
  
   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**删除**|单击此项可删除所选的映射。|  
   |**源文档**|从下拉列表中，选择要使用与此端口的源架构。|  
   |**地图**|从下拉列表中，选择你想要与此端口关联的映射。|  
   |**目标文档**|从下拉列表中，选择要使用与此端口的目标架构。|  
  
## <a name="see-also"></a>请参阅  
 [管理接收端口](../core/managing-receive-ports.md)   
 [管理映射](../core/managing-maps.md)