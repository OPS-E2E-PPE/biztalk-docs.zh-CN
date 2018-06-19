---
title: 如何配置为发送端口的出站映射 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, outbound maps
- configuring, send ports
- managing [send ports], configuring
- send ports, outbound maps
- send ports, configuring
- managing [send ports], outbound maps
ms.assetid: 9f5f5504-5a7f-4b21-9a65-91dce9d35890
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51d3feaba929d1a7585a8e7c3b29f6868dcc9dc7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248085"
---
# <a name="how-to-configure-outbound-maps-for-a-send-port"></a>如何为发送端口配置出站映射
本主题介绍如何通过使用 BizTalk Server 管理控制台来为发送端口配置出站映射。 可以使用映射对该发送端口发送的消息应用 XSL 转换，而无需通过业务流程来处理该消息。 您可以添加出站映射、删除映射或更改现有映射。 还可以向发送端口添加多个映射，但每个映射必须具有唯一的源架构。 有关地图背景信息，请参阅[映射](../core/maps.md)。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-configure-outbound-maps-for-a-send-port"></a>为发送端口配置出站映射  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开要为其配置出站映射的发送端口所属的 BizTalk 组和 BizTalk 应用程序。  
  
3.  展开**发送端口**，右键单击发送端口，请单击**属性**，然后单击**出站映射**。  
  
4.  下表中所述配置出站映射，然后单击**确定**。 可根据需要重复这些步骤来添加或删除多个映射。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**删除**|单击此项可删除所选映射。|  
    |**出站映射的源文档**|从下拉列表中选择出站映射的源文档。|  
    |**出站映射-映射**|从下拉列表中选择与源文档和目标文档关联的映射。|  
    |**出站映射的目标文档**|从下拉列表中选择出站映射的目标文档。|  
  
## <a name="see-also"></a>另请参阅  
 [创建和配置发送端口](../core/creating-and-configuring-send-ports.md)   
 [管理映射](../core/managing-maps.md)