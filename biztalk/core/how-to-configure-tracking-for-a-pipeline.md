---
title: "如何配置跟踪为管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [pipelines], tracking warning
- tracking, pipelines
- tracking, warnings
- configuring, pipelines
- pipelines, tracking
- managing [pipelines], configuring
- tracking, configuring
- pipelines, configuring
- configuring [HAT tracking], pipelines
- HAT, pipelines
- managing [pipelines], tracking
ms.assetid: 4f7f3c4a-4464-4170-a580-b4ce9296a097
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e933e9b50c99e11013ceaedf65c4f253ad1620c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-tracking-for-a-pipeline"></a>如何配置跟踪为管道
本主题将介绍如何使用 BizTalk Server 管理为管道配置跟踪。 您可能会希望配置跟踪以进行故障排除和审核。 您可以查看消息属性、端口事件和消息事件。 您还可以跟踪消息事件和消息的端口事件。  
  
 对于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中提供的任意默认管道或已部署到 BizTalk 应用程序中的自定义管道，您都可以配置跟踪功能。 您配置的跟踪设置适用于相应管道的所有实例。  
  
> [!IMPORTANT]
>  虽然可以为管道配置跟踪，但是，这将会生成大量的数据，因为这会对使用管道的所有端口全局性地收集数据。 我们建议改为你配置跟踪你发送和接收端口中, 所述[如何配置跟踪发送端口](../core/how-to-configure-tracking-for-a-send-port.md)和[如何配置跟踪接收端口](../core/how-to-configure-tracking-for-a-receive-port.md)。  
  
 有关跟踪的功能的消息事件和服务实例的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)  
  
## <a name="prerequisites"></a>先决条件  
 若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。 有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
### <a name="to-configure-tracking-for-a-pipeline"></a>为管道配置跟踪  
  
1.  单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。  
  
2.  在控制台树中，展开**BizTalk Server 管理**展开包含要为其配置跟踪管道的 BizTalk 组。  
  
3.  执行以下操作之一：  
  
    -   若要配置 BizTalk 管道跟踪的默认值之一，展开\<所有项目 >。  
  
    -   若要为已部署到 BizTalk 应用程序中的自定义管道配置跟踪，请展开包含该管道的应用程序。  
  
4.  单击**管道**文件夹，右键单击管道，，然后单击**跟踪**。  
  
    > [!NOTE]
    >  若要配置跟踪在一次，多个管道按住 Shift 键，单击要配置每个管道，右键单击其中一个管道，并依次**跟踪**。  
  
5.  下表中所述配置所需的跟踪选项，然后单击**确定**。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**端口的开始和结束事件**|选中此复选框则仅在实例开始和结束时进行跟踪。 详细信息包括项名称、程序集和其他元数据。|  
    |**消息发送和接收事件**|选中此复选框可跟踪消息发送和接收事件。 此复选框才可用才**端口开始和结束事件**选择。|  
    |**在管道处理之前的消息**|选中此复选框可保存并跟踪管道接收到的消息正文，其中包含诸如 URL 和已升级属性之类的元数据。 如果是接收管道，则消息正文部分是传输组件提交给该管道的原始消息。 根据相应的应用程序，可能对该消息进行加密、签名或编码。 在使用 BizTalk 映射时，如果这是接收管道，则在处理完入站映射后进行跟踪。<br /><br /> 此复选框才可用才**消息发送和接收事件**选择。|  
    |**在管道处理后的消息**|选中此复选框可保存并跟踪管道发送的消息正文，其中包含诸如 URL 和已升级属性之类的元数据。 如果是接收管道，则消息正文部分是提交给 MessageBox 数据库的已处理消息（它可以是 XML，这取决于相应的应用程序）。 在使用 BizTalk 映射时，如果这是发送管道，则在处理出站映射之前进行跟踪。<br /><br /> 此复选框才可用才**消息发送和接收事件**选择。|  
  
## <a name="see-also"></a>另请参阅  
 [管理管道](../core/managing-pipelines.md)