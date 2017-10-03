---
title: "手动配置到 SAP 适配器的物理端口绑定 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, sending messages to the SAP system
- physical port binding, manually configuring
- deploying, receiving messages from the SAP system
ms.assetid: c4f547aa-5514-4ca9-809b-d8d395de419c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 725a26eed4502e0a3d1eca8ed5f1429988590614
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="manually-configure-a-physical-port-binding-to-the-sap-adapter"></a>手动配置到 SAP 适配器的物理端口绑定
配置[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]为 WCF 自定义绑定使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 

## <a name="port-overview"></a>端口概述
在部署后适配器，你将能够发送和接收来自 SAP 系统的消息，通过使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 部署该适配器的步骤有所不同，具体取决于：  
  
-   之间的通信的方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 你可以选择配置发送、 接收、 发送-接收或接收发送端口。 下表对这些选项进行了概括介绍：  
  
    |端口方向|通信模式|可供选择的通信的方向|  
    |---|---|---|  
    |Send|单向|我将始终发送消息上此端口。|  
    |Receive|单向|始终在此端口上接收消息。|  
    |发送-接收|请求-响应|我将发送请求并接收响应。|  
    |接收-发送|请求作出响应|我将接收请求并发送响应。|  
  
     有关详细信息，请参阅[创建发送端口](../../core/how-to-create-a-send-port2.md)，或[创建接收端口](../../core/how-to-create-a-receive-port.md)。
  
-   是否适配器将消息发送到 SAP 系统，或从 SAP 系统接收消息。 具体取决于是否想要发送或接收消息，你将创建一个发送或接收端口。  
  
    > [!NOTE]
    >  你也可以配置发送或接收端口通过导入创建的绑定配置文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]作为元数据生成的一部分。 有关配置使用此绑定文件的端口的说明，请参阅[配置物理端口绑定使用的端口绑定文件，以便 SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)。
  
## <a name="in-this-section"></a>在本节中  
  
-   [配置使用 WCF 自定义适配器和 Oracle 数据库适配器的端口](../../adapters-and-accelerators/adapter-oracle-database/configure-a-port-using-the-wcf-custom-adapter-and-oracle-database-adapter.md)  
  
-   [配置使用 WCF SAP 适配器的端口](../../adapters-and-accelerators/adapter-sap/configure-a-port-using-the-wcf-sap-adapter.md)  
  
## <a name="see-also"></a>另请参阅  
[若要创建的 SAP 应用程序的构建基块](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)