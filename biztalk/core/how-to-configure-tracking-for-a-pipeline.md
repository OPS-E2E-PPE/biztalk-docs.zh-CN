---
title: "启用管道跟踪 |Microsoft 文档"
description: "跟踪消息正文和管道处理 BizTalk Server 中的消息时，事件"
ms.custom: 
ms.date: 12/13/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f7f3c4a-4464-4170-a580-b4ce9296a097
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ed836947ff47e21eeeb3bc306e94ea08f5464f0
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2017
---
# <a name="configure-pipeline-tracking-in-biztalk-server"></a>配置 BizTalk Server 中跟踪的管道
使用 BizTalk Server 管理来配置跟踪的管道。 您可能会希望配置跟踪以进行故障排除和审核。 您可以查看消息属性、端口事件和消息事件。 您还可以跟踪消息事件和消息的端口事件。  
  
 对于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中提供的任意默认管道或已部署到 BizTalk 应用程序中的自定义管道，您都可以配置跟踪功能。 您配置的跟踪设置适用于相应管道的所有实例。  
  
> [!IMPORTANT]
>  虽然你可以配置为管道的跟踪，这会生成大量的数据，因为为使用管道的所有端口全局收集数据。 相反，我们建议你配置跟踪你发送和接收端口中, 所述[发送端口配置跟踪](../core/how-to-configure-tracking-for-a-send-port.md)和[配置为接收端口跟踪](../core/how-to-configure-tracking-for-a-receive-port.md)。  
  
 有关跟踪的功能的消息事件和服务实例的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)  
  
## <a name="prerequisites"></a>必备条件  
使用 BizTalk Server Administrators 组的成员的帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="enable-pipeline-tracking"></a>启用管道跟踪
  
1.  在**BizTalk Server 管理**，展开包含管道的 BizTalk 组。 
  
2.  执行以下操作之一：  
  
    -   若要配置 BizTalk 管道跟踪的默认值之一，展开\<所有项目\>。  
  
    -   若要为已部署到 BizTalk 应用程序中的自定义管道配置跟踪，请展开包含该管道的应用程序。  
  
3.  选择**管道**文件夹中，右键单击管道，，然后选择**跟踪**。  
  
    > [!NOTE]
    >  若要配置跟踪，同时，多个管道按住 Shift 键，选择要配置每个管道，右键单击其中一个管道，，然后选择**跟踪**。  
  
4.  使用以下详细信息来配置跟踪所需的选项，然后选择**确定**以保存所做的更改。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**跟踪事件数-端口开始日期和结束事件**|仅当实例开始和结束时跟踪。 详细信息包括项名称、程序集和其他元数据。|  
    |**跟踪事件的消息发送和接收事件**|跟踪消息发送和接收事件。 仅可用**端口开始和结束事件**选择。|  
    |**跟踪消息正文-在管道处理之前的消息**|将保存并跟踪管道，其中包含元数据，例如 Url 并提升属性收到的消息正文。 如果是接收管道，则消息正文部分是传输组件提交给该管道的原始消息。 根据相应的应用程序，可能对该消息进行加密、签名或编码。 在使用 BizTalk 映射时，如果这是接收管道，则在处理完入站映射后进行跟踪。<br /><br /> 仅可用**消息发送和接收事件**选择。|  
    |**跟踪消息正文-在管道处理后的消息**|将保存并跟踪发送管道，其中包含元数据，例如 Url 并提升属性的消息正文。 如果是接收管道，则消息正文部分是提交给 MessageBox 数据库的已处理消息（它可以是 XML，这取决于相应的应用程序）。 在使用 BizTalk 映射时，如果这是发送管道，则在处理出站映射之前进行跟踪。<br /><br /> 仅可用**消息发送和接收事件**选择。|  
  
## <a name="see-also"></a>另请参阅  
 [管理管道](../core/managing-pipelines.md)
