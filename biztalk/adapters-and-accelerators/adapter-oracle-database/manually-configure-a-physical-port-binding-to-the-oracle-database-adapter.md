---
title: 手动配置到 Oracle 数据库适配器的物理端口绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, sending to an Oracle database
- messages, receiving from an Oracle database
- physical port binding, manually configuring
ms.assetid: 6b118236-e9eb-494e-96b2-969c7064943d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79e002762175eb847385617e2efd570d342b1c3a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976200"
---
# <a name="manually-configure-a-physical-port-binding-to-the-oracle-database-adapter"></a>手动配置到 Oracle 数据库适配器的物理端口绑定
本部分提供有关配置信息[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]作为 WCF 自定义绑定或通过使用 Wcf-oracledb 绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 在部署后，适配器，您将能够发送和接收消息从 Oracle 数据库使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 部署该适配器的步骤会有所不同，具体取决于：  
  
- BizTalk Server 之间的通信的方向和[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 您可以选择配置发送、 接收、 发送-接收或发送接收端口。 下表总结了你的选择。  
  
  |端口方向|通信模式|可供选择的通信方向|  
  |--------------------|---------------------------|-----------------------------------------------|  
  |Send|单向|我将始终在发送消息此端口上。|  
  |Receive|单向|始终在此端口上接收消息。|  
  |发送接收|请求-响应|我将发送请求并接收响应。|  
  |接收发送|要求响应|我将接收请求并发送响应。|  
  
   有关详细信息，请参阅[创建一个发送端口](../../core/how-to-create-a-send-port2.md)，或[创建一个接收端口](../../core/how-to-create-a-receive-port.md)。 
  
- 是否该适配器将消息发送到 Oracle 数据库或从 Oracle 数据库接收消息。 具体取决于是否想要发送或接收消息，将创建一个发送或接收端口，分别。  
  
  > [!NOTE]
  >  此外可以配置发送或接收端口通过导入创建的绑定配置文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]作为元数据生成的一部分。 有关使用此绑定文件配置端口的说明，请参阅[配置使用的 Oracle 数据库的端口绑定文件的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)。  
  
 
  
## <a name="see-also"></a>请参阅  
[开发 BizTalk 应用程序](../../core/develop-your-biztalk-applications.md)