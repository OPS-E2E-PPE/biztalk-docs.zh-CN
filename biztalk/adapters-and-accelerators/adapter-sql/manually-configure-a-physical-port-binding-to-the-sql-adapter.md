---
title: 手动配置到 SQL 适配器的物理端口绑定 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d3f0bb78-c85f-4629-9e2d-cce180ff78ae
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ac72d914539eabc9b129985c2b9335270e561d18
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222661"
---
# <a name="manually-configure-a-physical-port-binding-to-the-sql-adapter"></a>手动配置到 SQL 适配器的物理端口绑定
本部分提供有关配置信息[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]作为 WCF 自定义绑定或通过使用 WCF SQL 端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 在部署后适配器，你将能够发送和接收消息从 SQL Server 使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 部署该适配器的步骤有所不同，具体取决于：  
  
-   之间的通信的方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 你可以选择配置发送、 接收或发送接收端口。 下表概述了你的选择。  
  
    |端口方向|通信模式|可供选择的通信的方向|  
    |--------------------|---------------------------|-----------------------------------------------|  
    |Send|单向|我将始终发送消息上此端口。|  
    |Receive|单向|始终在此端口上接收消息。|  
    |发送接收|请求-响应|我将发送请求并接收响应。|  
  
    > [!NOTE]
    >  双向接收端口不受[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
     有关详细信息，请参阅[如何创建发送端口](../../core/how-to-create-a-send-port2.md)，或[如何创建接收端口](../../core/how-to-create-a-receive-port.md)。 
  
-   是否适配器将消息发送到 SQL Server （出站操作），或从 SQL Server （入站操作） 中接收消息。 具体取决于是否想要发送或接收消息，将创建一个发送或接收端口，分别。  
  
    > [!NOTE]
    >  你也可以配置发送或接收端口通过导入创建的绑定配置文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]作为元数据生成的一部分。 有关配置使用此绑定文件的端口的说明，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。
  
## <a name="in-this-section"></a>本节内容  
  
-   [配置使用 WCF 自定义适配器和 SQL 适配器的端口](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md)  
  
-   [配置使用 WCF SQL 适配器的端口](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-sql-adapter.md)  
  
## <a name="see-also"></a>另请参阅  
[开发具有 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)