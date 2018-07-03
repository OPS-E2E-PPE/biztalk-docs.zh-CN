---
title: 如何配置入站的映射接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- managing [receive ports], configuring
- configuring, maps
- configuring, inbound maps
- maps, configuring
- receive ports, configuring
- receive ports, inbound maps
- configuring, receive ports
- maps, inbound
- managing [receive ports], inbound maps
ms.assetid: b7448b39-f024-4353-818b-f753c2d60751
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b840f4c418c835765345adc01da5c9c18812d3ce
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985598"
---
# <a name="how-to-configure-inbound-maps-for-a-receive-port"></a>如何为接收端口配置入站映射
本主题将介绍如何使用 BizTalk Server 管理控制台为接收端口配置入站映射。 使用入站映射可以将入站消息从一种架构转换为另一种架构，例如，将从合作伙伴接收到的入站消息转换为您公司所使用的架构。  
  
 可以使用映射对该接收端口发送的消息应用 XSL 转换，而无需通过业务流程来处理该消息。 您可以添加入站映射、删除映射或更改现有映射。 可以为接收端口添加多个映射，但每个映射必须仅仅有唯一的源架构。 有关地图的背景信息，请参阅[映射](../core/maps.md)。  
  
> [!NOTE]
>  应用程序开发人员可以通过在开发过程中使用本主题中的过程来为接收端口配置映射。  
  
## <a name="prerequisites"></a>必要條件  
 若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-configure-inbound-maps-for-a-receive-port"></a>为接收端口配置入站映射  
  
1. 单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2. 在控制台树中，展开要为其配置入站映射的接收端口所属的 BizTalk 组和 BizTalk 应用程序。  
  
3. 单击**接收端口**，右键单击该接收端口，单击**属性**，然后单击**入站映射**。  
  
4. 下表中所述配置入站的映射，然后单击**确定**。  
  
   |使用此选项|执行的操作|  
   |--------------|----------------|  
   |**删除**|单击此项可删除所选映射。|  
   |**源文档**|从下拉列表中，选择要与此端口一起使用的源架构。|  
   |**地图**|从下拉列表中，选择要与此端口关联的映射。|  
   |**目标文档**|从下拉列表中，选择要与此端口一起使用的目标架构。|  
  
## <a name="see-also"></a>请参阅  
 [管理接收端口](../core/managing-receive-ports.md)   
 [管理映射](../core/managing-maps.md)