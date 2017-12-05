---
title: "生成 XSD 架构的 JSON 消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5453b76c-b282-442f-9eb1-6c2628b38ad5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88caf75d312179cd45bb1b3b421d6c2c7f25c2a8
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="generate-an-xsd-schema-for-json-message"></a>为 JSON 消息生成 XSD 架构
> [!NOTE]
>  本教程仅适用于 BizTalk Server。  
  
 在此解决方案中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序会收到 JSON 消息。 在应用程序处理此消息之前，必须先将此消息转换为 XSD 架构。 为此，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 提供了 JSON 架构向导，以便根据 JSON 消息创建 XSD 架构。  
  
1.  在 Visual Studio 中，新建一个 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目。  
  
2.  在解决方案资源管理器，右键单击项目名称 >**添加** > **新项** > **JSON 架构向导**。 提供架构名称 (`PO.xsd`)，然后单击**添加**。  
  
3.  在 JSON 架构向导中，在欢迎页上，单击**下一步**。  
  
4.  在“JSON 架构信息”页中，提供发送到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序的 JSON 采购订单文件的位置。 提供根节点名称，目标命名空间，，然后单击**完成**。  
  
     ![生成的 XSD 架构的 JSON](../core/media/btsjson-wizard.png "BTSJSON_Wizard")  
  
5.  具有指定名称的架构即会添加到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 项目中。 生成的架构文件 (**PO.xsd**) 还提供该示例。  
  
## <a name="see-also"></a>另请参阅  
 [使用 BizTalk Server 处理 JSON 消息](../core/processing-json-messages-using-biztalk-server.md)