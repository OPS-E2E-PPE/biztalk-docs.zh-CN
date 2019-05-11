---
title: 手动配置与 SQL 适配器的物理端口绑定 |Microsoft Docs
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
ms.openlocfilehash: 0fccfcfed0e965831d0c40ccde94348440db357e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368790"
---
# <a name="manually-configure-a-physical-port-binding-to-the-sql-adapter"></a>手动配置与 SQL 适配器的物理端口绑定
本部分提供有关配置信息[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]作为 WCF 自定义绑定或通过使用 WCF SQL 端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 在部署后，适配器，您将能够发送和接收消息从 SQL Server 使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 部署该适配器的步骤会有所不同，具体取决于：  
  
- 之间的通信方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 您可以选择配置发送、 接收或发送接收端口。 下表总结了你的选择。  
  
  |端口方向|通信模式|可供选择的通信方向|  
  |--------------------|---------------------------|-----------------------------------------------|  
  |Send|单向|我将始终在发送消息此端口上。|  
  |Receive|单向|我始终将接收此端口上的消息。|  
  |发送接收|请求-响应|我将发送请求并接收响应。|  
  
  > [!NOTE]
  >  双向接收端口不受[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
   有关详细信息，请参阅[如何创建发送端口](../../core/how-to-create-a-send-port2.md)，或[如何创建接收端口](../../core/how-to-create-a-receive-port.md)。 
  
- 是否该适配器将消息发送到 SQL Server （出站操作），或从 SQL Server （入站操作） 接收消息。 具体取决于是否想要发送或接收消息，将创建一个发送或接收端口，分别。  
  
  > [!NOTE]
  >  此外可以配置发送或接收端口通过导入创建的绑定配置文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]作为元数据生成的一部分。 有关使用此绑定文件配置端口的说明，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用 WCF 自定义适配器和 SQL 适配器配置端口](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md)  
  
-   [使用 WCF-SQL 适配器配置端口](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-sql-adapter.md)  
  
## <a name="see-also"></a>请参阅  
[若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)