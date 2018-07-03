---
title: SQL 适配器常见问题解答 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 25369e6b-d1f2-4abc-9ffc-4cb9aef1d3fb
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 83d94b47a7475e53d15e4f7866dea36bf1fcf08b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978478"
---
# <a name="sql-adapter-faqs"></a>SQL 适配器常见问题解答
以下一些常见问题 (Faq) 与相关[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]和[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]一般情况下。  
  
## <a name="how-can-i-use-the-sql-adapter-to-communicate-with-the-sql-server-database"></a>如何使用 SQL 适配器与 SQL Server 数据库进行通信？  
 可以使用 SQL 适配器与 SQL Server 数据库，方法是通过开发 BizTalk 应用程序、 使用 WCF 服务模型或使用 WCF 通道模型进行通信。 有关详细信息，请参阅[概述的 BizTalk 适配器适用于 SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)。  
  
## <a name="what-interfaces-are-supported-by-the-sql-adapter-for-retrieving-metadata"></a>SQL 适配器支持哪些接口用于检索元数据？  
 SQL 适配器为检索元数据支持两个接口：  
  
-   MetadataExchange WCF 提供的。 WCF 提供了元数据交换终结点的所有 WCF 绑定，它允许客户端从 SQL Server 数据库中获取元数据。  
  
-   IMetadataRetrievalContract 提供的 WCF LOB 适配器 SDK 的说明进行操作，它支持的元数据浏览和搜索功能的适配器。  
  
## <a name="how-does-the-sql-adapter-support-high-availability-of-data"></a>SQL 适配器如何支持数据的高可用性？  
 同时指定[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)要连接到 SQL Server 数据库，SQL 适配器，可指定要连接到主 SQL Server 数据库的故障转移 SQL Server 数据库的名称不是可用。 使用可选参数，FailoverPartner，连接 URI 中的指定故障转移 SQL Server 数据库。  
  
## <a name="can-i-migrate-biztalk-projects-created-using-the-previous-version-of-the-sql-adapter-to-use-the-wcf-based-sql-adapter-how"></a>可以将迁移创建使用以前版本的 SQL 适配器为使用基于 WCF 的 SQL 适配器的 BizTalk 项目？ 如何操作？  
 是。 若要了解使用以前版本的 SQL 适配器为使用基于 WCF 的 SQL 适配器创建的迁移 BizTalk 项目的步骤，请参阅[SQL 适配器教程](../../adapters-and-accelerators/adapter-sql/sql-adapter-tutorials.md)。  
  
## <a name="does-the-sql-adapter-provide-a-secure-way-of-communicating-with-the-sql-server-database--are-there-any-best-practices-to-ensure-security-of-data"></a>SQL 适配器是否提供与 SQL Server 数据库进行通信的安全方式？  是否有任何最佳实践，以确保数据的安全性？  
 SQL 适配器支持企业单一登录 (SSO) 和集成安全性建立与 SQL Server 数据库的连接上进行身份验证。 通过 SSO，凭据进行加密和存储在注册表中。 系统使用这些凭据来确定而不是要求用户输入其位置可能会看到这些功能由未经授权的参与者访问权限。 集成的安全性使用登录用户的凭据来访问 SQL server。 这还消除了需要用户输入凭据。 数据库管理员必须配置 SQL 以接受用户的凭据为使用集成安全性才能正常工作。  
  
 SQL 适配器也不允许您在 SQL Server 数据库的连接 URI 添加适配器服务参考 Visual Studio 插件和使用适配器服务的 BizTalk 项目外接程序以防止在使用时输入的用户凭据从以明文形式显示的凭据。 此外，密码不会写入到配置文件 （由添加适配器服务参考 Visual Studio 插件生成） 和绑定生成的文件 （使用适配器服务的 BizTalk 项目外接程序） 中。  
  
 有关详细信息：  
  
- 中的数据安全性[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[保护 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)。  
  
- 最佳实践，以确保中的数据安全性[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[最佳做法来保护 SQL 适配器](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)。  
  
## <a name="is-there-a-gui-provided-by-the-sql-adapter-to-view-and-perform-operations-on-the-artifacts-in-my-underlying-sql-server-database"></a>是否有 SQL 适配器提供的 GUI 来查看并执行我基础 SQL Server 数据库中的项目上的操作？  
 使用适配器服务的 BizTalk 项目外接程序和添加适配器服务参考 Visual Studio 插件提供一个对话框，您可以在其中查看并在基础 SQL Server 数据库中执行对项目的操作。 有关 SQL 适配器提供的图形用户界面的详细信息，请参阅[浏览、 搜索和获取元数据的 SQL 操作使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter.md)。  
  
## <a name="what-are-binding-properties-in-the-sql-adapter-where-can-i-find-information-about-all-the-binding-properties-in-sql-adapter"></a>什么 SQL 适配器中绑定属性？ 在哪里可以找到有关所有绑定属性的信息中 SQL 适配器？  
 适配器客户端可以使用中的绑定属性[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]若要配置和控制适配器的行为。 对于所有的绑定属性信息显示在[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[了解关于 BizTalk Adapter for SQL Server 适配器绑定属性](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
## <a name="what-is-msdtc-do-i-need-to-bother-about-it-before-using-sql-adapter"></a>MSDTC 是什么？ 我是否需要使用 SQL 适配器之前费心？  
 MSDTC 代表 Microsoft 分布式事务处理协调器。 MSDTC 协调多个资源管理器，例如数据库、 文件系统和消息队列之间的各种事务。 若要使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，必须先启用 MSDTC。 有关配置 MSDTC 的详细信息，请参阅[SQL Server 和适配器客户端上配置 MSDTC](../../adapters-and-accelerators/adapter-sql/configure-msdtc-on-sql-server-and-adapter-client.md)。  
  
## <a name="where-can-i-find-information-about-the-sql-server-data-types-that-are-supported-in-the-sql-adapter"></a>在哪里可以找到有关 SQL 适配器支持的 SQL Server 数据类型的信息？  
 若要了解有关 SQL 适配器支持的 SQL Server 数据类型的信息，请参阅[基本 SQL Server 数据类型](../../adapters-and-accelerators/adapter-sql/basic-sql-server-data-types.md)。  
  
## <a name="which-approach-biztalk-server-wcf-service-model-or-wcf-channel-model-can-i-use-to-perform-various-operations-using-the-sql-adapter"></a>我可以使用哪种方法 （BizTalk Server 中，WCF 服务模型或 WCF 通道模型） 来使用 SQL 适配器执行各种操作？  
 若要了解有关可用于使用 SQL 适配器执行各种操作方法的更多信息，请参阅[开发 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)。  
  
 
## <a name="see-also"></a>请参阅  
 [方面的常见问题](../../adapters-and-accelerators/frequently-asked-questions-for-the-biztalk-adapter-pack.md)
 