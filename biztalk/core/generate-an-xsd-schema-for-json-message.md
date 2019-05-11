---
title: 生成 XSD 架构为 JSON 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5453b76c-b282-442f-9eb1-6c2628b38ad5
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1f44b18593e756fe1ed6e05e03d62e498f66c0a3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387763"
---
# <a name="generate-an-xsd-schema-for-json-message"></a>生成 XSD 架构为 JSON 消息
> [!NOTE]
>  本教程仅适用于 BizTalk Server。  
  
 在此解决方案中，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序接收 JSON 消息。 应用程序能够处理该消息之前，它必须转换为 XSD 架构。 为此，请[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供了从 JSON 消息创建 XSD 架构的 JSON 架构向导。  
  
1. 在 Visual Studio 中，创建一个新[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目。  
  
2. 在解决方案资源管理器，右键单击项目名称 >**外** > **新项** > **JSON 架构向导**。 提供架构的名称 (`PO.xsd`)，然后单击**添加**。  
  
3. 在 JSON 架构向导中，在欢迎页上，单击**下一步**。  
  
4. 在 JSON 架构信息页中提供的 JSON 采购订单文件发送到的位置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序。 提供根节点名、 目标命名空间，并单击**完成**。  
  
    ![生成的 XSD 架构的 JSON](../core/media/btsjson-wizard.png "BTSJSON_Wizard")  
  
5. 具有指定名称的架构添加到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]项目。 生成的架构文件 (**PO.xsd**) 还提供的示例。  
  
## <a name="see-also"></a>请参阅  
 [使用 BizTalk Server 处理 JSON 消息](../core/processing-json-messages-using-biztalk-server.md)