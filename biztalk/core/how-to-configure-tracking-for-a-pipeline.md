---
title: 启用管道跟踪 |Microsoft Docs
description: 跟踪消息正文和管道处理 BizTalk Server 中的消息时的事件
ms.custom: ''
ms.date: 12/13/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4f7f3c4a-4464-4170-a580-b4ce9296a097
caps.latest.revision: 18
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 689d5395d75a558e3f437c4a3efea13c70f593e4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385871"
---
# <a name="configure-pipeline-tracking-in-biztalk-server"></a>跟踪 BizTalk Server 中的管道配置
使用 BizTalk Server 管理为管道配置跟踪。 您可能想要配置用于故障排除和审核目的的跟踪。 您可以查看消息属性、 端口事件和消息事件。 您还可以跟踪消息事件和消息的端口事件。  
  
 您可以配置跟踪功能的任意默认管道中包含[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]或已部署到 BizTalk 应用程序中的自定义管道。 你配置的跟踪设置适用于所有管道的实例。  
  
> [!IMPORTANT]
>  尽管可以配置跟踪的管道，但因为使用管道的所有端口全局性地都收集数据这会生成大量的数据。 相反，我们建议你配置跟踪上发送和接收端口，如中所述[为发送端口配置跟踪](../core/how-to-configure-tracking-for-a-send-port.md)并[配置为接收端口跟踪](../core/how-to-configure-tracking-for-a-receive-port.md)。  
  
 有关消息事件和服务实例跟踪功能的详细信息[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，请参阅[查看跟踪消息和实例数据](../core/viewing-tracked-message-and-instance-data.md)  
  
## <a name="prerequisites"></a>先决条件  
使用 BizTalk Server Administrators 组的成员帐户登录。 有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。  
  
## <a name="enable-pipeline-tracking"></a>启用管道跟踪
  
1.  在中**BizTalk Server 管理**，包含管道的 BizTalk 组。 
  
2.  执行以下操作之一：  
  
    -   若要配置跟踪的默认 BizTalk 管道，请展开\<的所有项目\>。  
  
    -   若要配置已部署到 BizTalk 应用程序的自定义管道的跟踪，请展开包含管道的应用程序。  
  
3.  选择**管道**文件夹中，右键单击该管道，然后选择**跟踪**。  
  
    > [!NOTE]
    >  要在一次，多个管道按住 Shift 键，选择要配置每个管道配置跟踪，请右键单击一个管道，并选择**跟踪**。  
  
4.  使用以下详细信息来配置的跟踪选项，然后选择**确定**以保存所做的更改。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**跟踪事件-端口开始和结束事件**|仅当实例开始和结束跟踪。 详细信息包括项名称、 程序集和其他元数据。|  
    |**跟踪事件-消息发送和接收事件**|跟踪消息发送和接收事件。 只有**端口开始和结束事件**处于选中状态。|  
    |**跟踪消息正文-管道处理前的消息**|保存并跟踪管道，其中包含元数据，例如 Url 和升级属性收到的消息正文。 如果这是接收管道，消息正文是原始消息由传输组件提交到管道。 根据应用程序，该消息可能加密、 签名，或编码。 在使用 BizTalk 映射时，如果这是接收管道，跟踪都将处理入站的映射后进行。<br /><br /> 只有**消息发送和接收事件**处于选中状态。|  
    |**跟踪消息正文-管道处理后的消息**|保存并跟踪管道，其中包含元数据，例如 Url 和升级的属性发送的消息正文。 如果这是接收管道，消息正文是已处理的消息提交到 MessageBox 数据库，这可以是 XML，具体取决于你的应用程序。 在使用 BizTalk 映射时，如果这是发送管道，跟踪都将处理出站映射之前进行。<br /><br /> 只有**消息发送和接收事件**处于选中状态。|  
  
## <a name="see-also"></a>请参阅  
 [管理管道](../core/managing-pipelines.md)
