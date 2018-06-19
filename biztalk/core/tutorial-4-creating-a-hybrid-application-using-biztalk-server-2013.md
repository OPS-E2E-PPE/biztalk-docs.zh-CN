---
title: 教程 4： 创建使用 BizTalk Server 2013 的混合应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3a9de95f-7d2c-437d-be5b-0062592f32c6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c11b163f34a1320052de585c7ddfc79afb03db4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22287341"
---
# <a name="tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013"></a>教程 4： 创建使用 BizTalk Server 2013 的混合应用程序
本部分提供了有关如何创建包含[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]和 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的混合应用程序的分步概览。  
  
## <a name="business-scenario"></a>业务方案  
 Northwind 是一家接收合作伙伴（其中之一为 Contoso）销售订单（以平面文件 EDI 消息的形式）的企业。 Northwind 希望设置一个执行以下操作的端到端应用程序：  
  
-   **管理 EDI 消息处理**– 此模块的应用程序必须验证从 Contoso 接收的消息是否符合标准的 EDI 消息格式。 此模块还必须生成所有必需的确认以验证是否成功处理了消息。  
  
-   **使用业务逻辑处理数据**– 后成功验证和处理 EDI 消息，Northwind 必须对用于进一步处理的业务逻辑运行消息。 例如，如果所收到消息中的订单数量超出了给定数量，则将数据存储在 SQL Server 数据库中， 否则会将数据发送到共享文件位置。  
  
 为了实现此方案，Northwind 决定设置一个混合应用程序，其中 EDI 消息处理在云中完成，业务逻辑驱动的数据处理则在本地完成。 为了设置此混合应用程序，Northwind 使用了以下项：  
  
-   **[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]**– 适用于 Azure BizTalk 门户[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]使客户能够在上配置贸易合作伙伴和 EDI 协议[!INCLUDE[winazure](../includes/winazure-md.md)]。 Northwind 使用[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]（2012 年 4 月版）来创建和部署该协议，该协议将处理传入的 EDI 消息，根据 X12 840 销售订单架构对其进行验证，将其转换为 Northwind 所需的架构，然后将其发送到 Service Bus 队列。 因此，为了开发混合应用程序，应将数据从 Service Bus 队列发送到用户所在场所的应用程序。  
  
-   **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**– 服务总线的新适配器 (**SB 消息**) 适用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使应用程序以接收来自像队列一样，主题，服务总线实体的消息，依此类推到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 作为的一部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序，Northwind 使用业务流程来确定收到的销售订单中请求的数量是否大于 100。 如果数量为大于 100，将消息插入 SQL Server 数据库表调用**SalesOrder**。 如果该数量小于 100，则将消息发送到共享文件位置。  
  
     为了将消息插入 SQL Server 数据库表，Northwind 使用作为 [!INCLUDE[adaptersql](../includes/adaptersql-md.md)] 的一部分提供的[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。  
  
### <a name="end-to-end-message-flow"></a>端到端消息流  
 以下说明了消息如何流经混合应用程序：  
  
1.  Contoso 将一个 X12 销售订单消息发送至终结点，该终结点已在云中部署了 EDI 协议。  
  
2.  通过 EDI 协议成功处理该消息后，再将其发送到 Service Bus 队列。  
  
3.  SB 消息接收适配器处理来自 Service Bus 队列的消息，并实例化 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中部署的业务流程，以便根据订单数量将消息发送到不同目标。  
  
4.  业务流程的订购数量大于 100，如果插入到消息**SalesOrder**表。 如果订购数量小于或等于 100，则将消息写入到共享文件位置。  
  
## <a name="set-up-your-computer"></a>设置计算机  
 本教程要求你执行四大活动。 下表列出了各种活动以及每个活动的软件要求：  
  
|活动|必需软件|  
|--------------|-----------------------|  
|创建 EDI 协议所需的 EDI 项目|本教程是使用[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]（2012 年 4 月版）和 X12 840 销售订单架构创建的。 可以从下载这些[http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057)。|  
|创建和部署 EDI 协议|由于 EDI 协议是部署到 Azure 上，因此，你仅需要一个 Web 浏览器（如 Internet Explorer）登录到 Azure BizTalk Portal 即可。|  
|构建、部署和配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 应用程序|如果你要设置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机上 Azure VM，请遵循的说明[http://msdn.microsoft.com/library/azure/jj248689.aspx](http://msdn.microsoft.com/library/azure/jj248689.aspx)。|  
|向 EDI 协议终结点发送测试消息|你可以使用[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]附带的示例程序包中提供的 MessageSender 工具。 你可以下载示例包从[http://go.microsoft.com/fwlink/p/?LinkId=235057](http://go.microsoft.com/fwlink/p/?LinkId=235057)。|  
  
 你可以选择在同一计算机上安装所有这些项目，也可以在不同计算机上进行安装。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [（适用于 Azure) 中的步骤 1： 创建 EDI 项目](../core/step-1-for-azure-create-the-edi-project.md)  
  
-   [（适用于 Azure) 中的步骤 2： 创建一个 EDI 协议](../core/step-2-for-azure-create-an-edi-agreement.md)  
  
-   [（适用于 Azure) 中的步骤 3： 创建 Service Bus 队列](../core/step-3-for-azure-create-a-service-bus-queue.md)  
  
-   [步骤 4 （在本地）： 创建 SQL Server 表](../core/step-4-on-premises-create-the-sql-server-table.md)  
  
-   [步骤 5 （在本地）： 生成插入消息 inito SalesOrder 表的架构](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md)  
  
-   [步骤 6 （在本地）： 创建一个可映射到 Insert 架构从队列消息的转换](../core/step-6-map-the-message-from-the-queue-to-the-insert-schema.md)  
  
-   [步骤 7 （在本地）： 创建业务流程](../core/step-7-on-premises-create-an-orchestration.md)  
  
-   [步骤 8 （在本地）： 配置 BizTalk Server 应用程序](../core/step-8-on-premises-configure-the-biztalk-server-application.md)  
  
-   [步骤 9： 测试解决方案](../core/step-9-test-the-solution.md)