---
title: "手动配置到 Oracle 数据库适配器的物理端口绑定 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, sending to an Oracle database
- messages, receiving from an Oracle database
- physical port binding, manually configuring
ms.assetid: 6b118236-e9eb-494e-96b2-969c7064943d
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d2a64223485cf83fb214055cb1e11b44fb6bc7c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="manually-configure-a-physical-port-binding-to-the-oracle-database-adapter"></a>手动配置到 Oracle 数据库适配器的物理端口绑定
本部分提供有关配置信息[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]作为 WCF 自定义绑定或通过使用 WCF OracleDB 绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 在部署后适配器，你将能够发送和接收消息从 Oracle 数据库使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 部署该适配器的步骤有所不同，具体取决于：  
  
-   BizTalk Server 之间的通信的方向和[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 你可以选择配置发送、 接收、 发送-接收或接收发送端口。 下表概述了你的选择。  
  
    |端口方向|通信模式|可供选择的通信的方向|  
    |--------------------|---------------------------|-----------------------------------------------|  
    |Send|单向|我将始终发送消息上此端口。|  
    |Receive|单向|始终在此端口上接收消息。|  
    |发送接收|请求-响应|我将发送请求并接收响应。|  
    |接收发送|请求作出响应|我将接收请求并发送响应。|  
  
     有关详细信息，请参阅[创建发送端口](../../core/how-to-create-a-send-port2.md)，或[创建接收端口](../../core/how-to-create-a-receive-port.md)。 
  
-   是否适配器将消息发送到 Oracle 数据库或从 Oracle 数据库中接收消息。 具体取决于是否想要发送或接收消息，将创建一个发送或接收端口，分别。  
  
    > [!NOTE]
    >  你也可以配置发送或接收端口通过导入创建的绑定配置文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]作为元数据生成的一部分。 有关配置使用此绑定文件的端口的说明，请参阅[配置使用端口绑定文件到 Oracle 数据库的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)。  
  
 
  
## <a name="see-also"></a>另请参阅  
[开发你的 BizTalk 应用程序](../../core/develop-your-biztalk-applications.md)