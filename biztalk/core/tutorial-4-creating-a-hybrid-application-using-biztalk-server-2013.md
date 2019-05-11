---
title: 教程 4:创建混合应用程序使用 BizTalk Server 2013 |Microsoft Docs
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
ms.openlocfilehash: 82d3f7a9b8cb4a59cf0be2d409a80004e8e5c504
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399180"
---
# <a name="tutorial-4-creating-a-hybrid-application-using-biztalk-server-2013"></a>教程 4:创建混合应用程序使用 BizTalk Server 2013
本部分提供有关如何创建混合应用程序涉及的分步演练[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  

## <a name="business-scenario"></a>业务方案  
 Northwind 是从其伙伴处，其中一个接收销售订单的企业为 Contoso，平面文件 EDI 消息的形式。 Northwind 希望设置端到端应用程序，执行以下任务：  

- **管理 EDI 消息处理**– 此模块应用程序必须验证从 Contoso 接收的消息是否符合标准的 EDI 消息格式。 此模块还必须生成所有必需的确认以验证已成功处理该消息。  

- **使用业务逻辑来处理数据**– 后已成功验证和处理 EDI 消息，Northwind 必须针对进行进一步处理的业务逻辑运行消息。 例如，如果收到的消息中的订单数量大于给定数量，数据存储在 SQL Server 数据库。 否则，将数据发送到共享的文件位置。  

  为了实现此方案，Northwind 决定设置一个混合应用程序，其中 EDI 消息处理是在云中完成时在本地完成业务逻辑驱动数据处理。 若要设置此混合应用程序，Northwind 使用以下：  

- **[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]**  – 适用于在 Azure BizTalk 门户[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]使客户能够在配置贸易合作伙伴和 EDI 协议[!INCLUDE[winazure](../includes/winazure-md.md)]。 Northwind 使用[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]– 2012 年 4 月发布，若要创建和部署处理传入的 EDI 消息，X12 840 销售订单架构中，转换到架构的消息所必需的 Northwind，，然后发送的消息对其进行验证的协议向服务总线队列。 因此，若要开发混合应用程序，数据应将从发送服务总线队列的本地应用程序。  

- **[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**  – 服务总线新适配器 (**Sb-messaging**) 适用于[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使应用程序以接收来自服务总线实体，例如队列、 主题、 消息等到[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 作为的一部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序中，Northwind 使用一个业务流程来确定收到的销售订单中请求的数量是否大于 100。 如果该数量大于 100，将消息插入到名为的 SQL Server 数据库表**SalesOrder**。 如果数量小于 100，则将消息发送到共享的文件位置。  

   若要将消息插入到 SQL Server 数据库表，Northwind 使用[!INCLUDE[adaptersql](../includes/adaptersql-md.md)]可作为的一部分[!INCLUDE[adapterpacknoversion](../includes/adapterpacknoversion-md.md)]。  

### <a name="end-to-end-message-flow"></a>端到端消息流  
 这是消息如何流经混合应用程序：  

1. Contoso 将 X12 销售订单消息到终结点在云部署 EDI 协议所在。  

2. 通过 EDI 协议成功处理消息后，它是发送到服务总线队列。  

3. SB 消息接收适配器处理来自服务总线队列的消息和实例化部署中的业务流程[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将消息发送到不同的目标根据订单数量。  

4. 如果订购数量大于 100，该业务流程将插入到消息**SalesOrder**表。 如果订购数量小于或等于 100，则将消息写入共享的文件位置。  

## <a name="set-up-your-computer"></a>设置计算机  
 本教程需要你执行四大活动。 下表列出了活动和每个活动的软件要求：  


|                                                            活动                                                             |                                                                                                                                              所需的软件                                                                                                                                               |
|---------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                     创建 EDI 协议所需的 EDI 项目                                     | 本教程使用创建[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]– 2012 年 4 月版本和 X12 840 销售订单架构。 可以从下载这些[ http://go.microsoft.com/fwlink/p/?LinkId=235057 ](http://go.microsoft.com/fwlink/p/?LinkId=235057)。 |
|                                               创建并部署 EDI 协议                                               |                                                                                 因为在 Azure 上部署 EDI 协议后，只需 Web 浏览器 (如 Internet Explorer) 登录到 Azure BizTalk 门户。                                                                                  |
| 生成、 部署和配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]应用程序 |              如果想要预配[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]计算机上 Azure VM，请遵循的说明[ http://msdn.microsoft.com/library/azure/jj248689.aspx ](http://msdn.microsoft.com/library/azure/jj248689.aspx)。               |
|                                        将测试消息发送到 EDI 协议终结点                                        |   可以使用软件包附带的示例中提供的 MessageSender 工具[!INCLUDE[appfabricintegration](../includes/appfabricintegration-md.md)]。 可以从示例包下载[ http://go.microsoft.com/fwlink/p/?LinkId=235057 ](http://go.microsoft.com/fwlink/p/?LinkId=235057)。   |

 您可以选择安装在同一计算机上或不同计算机上所有这些项。  

## <a name="in-this-section"></a>本节内容  

-   [步骤 1 （适用于 Azure):创建 EDI 项目](../core/step-1-for-azure-create-the-edi-project.md)  

-   [步骤 2 （适用于 Azure):创建 EDI 协议](../core/step-2-for-azure-create-an-edi-agreement.md)  

-   [步骤 3 （适用于 Azure):创建服务总线队列](../core/step-3-for-azure-create-a-service-bus-queue.md)  

-   [步骤 4 （本地）：创建 SQL Server 表](../core/step-4-on-premises-create-the-sql-server-table.md)  

-   [步骤 5 （本地）：生成插入消息用于向 SalesOrder 表的架构](../core/step-5-generate-the-schema-for-inserting-a-message-into-salesorder-table.md)  

-   [步骤 6 （本地）：创建一个转换，以便将消息从队列到插入架构映射](../core/step-6-map-the-message-from-the-queue-to-the-insert-schema.md)  

-   [步骤 7 （本地）：创建业务流程](../core/step-7-on-premises-create-an-orchestration.md)  

-   [步骤 8 （本地）：配置 BizTalk Server 应用程序](../core/step-8-on-premises-configure-the-biztalk-server-application.md)  

-   [步骤 9：测试解决方案](../core/step-9-test-the-solution.md)