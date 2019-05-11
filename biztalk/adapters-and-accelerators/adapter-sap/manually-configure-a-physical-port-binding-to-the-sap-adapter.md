---
title: 手动配置到 SAP 适配器的物理端口绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, sending messages to the SAP system
- physical port binding, manually configuring
- deploying, receiving messages from the SAP system
ms.assetid: c4f547aa-5514-4ca9-809b-d8d395de419c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3011bea808e59ec0ee80f3ac030937a9987d9233
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373250"
---
# <a name="manually-configure-a-physical-port-binding-to-the-sap-adapter"></a>手动配置到 SAP 适配器的物理端口绑定
配置[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]为使用自定义 WCF 绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 

## <a name="port-overview"></a>端口概述
在部署后，适配器，您将能够发送和接收来自 SAP 系统的消息，通过使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 部署该适配器的步骤会有所不同，具体取决于：  
  
- 之间的通信方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。 您可以选择配置发送、 接收、 发送-接收端口或接收发送端口。 下表总结了你的选择：  
  
  |端口方向|通信模式|可供选择的通信方向|  
  |---|---|---|  
  |Send|单向|我将始终在发送消息此端口上。|  
  |Receive|单向|我始终将接收此端口上的消息。|  
  |发送接收|请求-响应|我将发送请求并接收响应。|  
  |接收发送|要求响应|我将接收请求并发送响应。|  
  
   有关详细信息，请参阅[创建一个发送端口](../../core/how-to-create-a-send-port2.md)，或[创建一个接收端口](../../core/how-to-create-a-receive-port.md)。
  
- 是否该适配器将消息发送到 SAP 系统，或接收来自 SAP 系统的消息。 具体取决于是否想要发送或接收消息，将创建一个发送或接收端口。  
  
  > [!NOTE]
  >  此外可以配置发送或接收端口通过导入创建的绑定配置文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]作为元数据生成的一部分。 有关使用此绑定文件配置端口的说明，请参阅[配置物理端口绑定使用的端口绑定文件与 SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)。
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 WCF 自定义适配器和 Oracle 数据库适配器配置端口](../../adapters-and-accelerators/adapter-oracle-database/configure-a-port-using-the-wcf-custom-adapter-and-oracle-database-adapter.md)  
  
-   [使用 WCF-SAP 适配器配置端口](../../adapters-and-accelerators/adapter-sap/configure-a-port-using-the-wcf-sap-adapter.md)  
  
## <a name="see-also"></a>请参阅  
[生成块以创建 SAP 应用程序](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)