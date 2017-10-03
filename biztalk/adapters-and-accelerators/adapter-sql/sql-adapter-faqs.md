---
title: "SQL 适配器常见问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25369e6b-d1f2-4abc-9ffc-4cb9aef1d3fb
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9dee4b402e548f55dd8eab4583215d879c98186b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="sql-adapter-faqs"></a>SQL 适配器常见问题
以下一些常见问题 (Faq) 与相关[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]和[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]一般情况下。  
  
## <a name="how-can-i-use-the-sql-adapter-to-communicate-with-the-sql-server-database"></a>如何使用 SQL 适配器与 SQL Server 数据库进行通信？  
 SQL 适配器可用于与 SQL Server 数据库，方法是通过开发 BizTalk 应用程序、 使用 WCF 服务模型或使用 WCF 通道模型进行通信。 有关详细信息，请参阅[概述的 BizTalk Adapter for SQL Server](../../adapters-and-accelerators/adapter-sql/overview-of-biztalk-adapter-for-sql-server.md)。  
  
## <a name="what-interfaces-are-supported-by-the-sql-adapter-for-retrieving-metadata"></a>为检索元数据的 SQL 适配器支持哪些接口？  
 SQL 适配器为检索元数据支持两个接口：  
  
-   MetadataExchange WCF 提供的。 WCF 提供了元数据交换终结点的所有 WCF 绑定，这使客户端可以从 SQL Server 数据库中获取元数据。  
  
-   IMetadataRetrievalContract 由 WCF LOB 适配器 SDK 的说明进行操作，它支持浏览和搜索功能的适配器的元数据。  
  
## <a name="how-does-the-sql-adapter-support-high-availability-of-data"></a>SQL 适配器如何支持高可用性的数据？  
 指定时[创建 SQL Server 连接 URI](../../adapters-and-accelerators/adapter-sql/create-the-sql-server-connection-uri.md)要连接到 SQL Server 数据库，SQL 适配器允许您指定要连接到如果主 SQL Server 数据库故障转移 SQL Server 数据库的名称不是可用。 使用可选参数，FailoverPartner，连接 URI 中的指定故障转移 SQL Server 数据库。  
  
## <a name="can-i-migrate-biztalk-projects-created-using-the-previous-version-of-the-sql-adapter-to-use-the-wcf-based-sql-adapter-how"></a>可以将迁移使用以前版本的 SQL 适配器以使用基于 WCF 的 SQL 适配器创建 BizTalk 项目？ 如何？  
 是。 若要了解使用以前版本的 SQL 适配器以使用基于 WCF 的 SQL 适配器创建的迁移 BizTalk 项目的步骤，请参阅[SQL 适配器教程](../../adapters-and-accelerators/adapter-sql/sql-adapter-tutorials.md)。  
  
## <a name="does-the-sql-adapter-provide-a-secure-way-of-communicating-with-the-sql-server-database--are-there-any-best-practices-to-ensure-security-of-data"></a>SQL 适配器是否提供个与 SQL Server 数据库通信的安全方式？  是否有任何最佳实践，以确保数据安全？  
 SQL 适配器上建立与 SQL Server 数据库的连接进行身份验证支持企业单一登录 (SSO) 和集成安全性。 使用 SSO，凭据进行加密和存储在注册表中。 系统使用这些凭据来确定而不是要求用户输入其中他们可能看到未经授权的参与者的访问权限。 集成的安全性使用登录用户的凭据来访问 SQL server。 这还消除了对用户输入凭据的需要。 数据库管理员必须配置 SQL 接受集成安全性才能正常工作的用户的凭据。  
  
 SQL 适配器同样不允许你在 SQL Server 数据库连接 URI 时使用的添加适配器服务引用 Visual Studio 插件和使用适配器服务 BizTalk 项目外接程序以防止中输入用户凭据显示以明文形式的凭据。 此外，密码不会写入到配置文件 （由添加适配器服务引用 Visual Studio 插件生成） 和绑定生成的文件 （使用适配器服务 BizTalk 项目外接程序） 中。  
  
 有关详细信息：  
  
-   中的数据安全性[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[保护 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/secure-your-sql-applications.md)。  
  
-   最佳做法，以确保中的数据安全性[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[最佳做法来保护 SQL 适配器](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)。  
  
## <a name="is-there-a-gui-provided-by-the-sql-adapter-to-view-and-perform-operations-on-the-artifacts-in-my-underlying-sql-server-database"></a>是否有 SQL 适配器提供一个 GUI，以查看和我基础的 SQL Server 数据库中执行操作的项目？  
 使用适配器服务 BizTalk 项目外接程序和添加适配器服务引用 Visual Studio 插件提供一个对话框，你可以在其中查看和基础 SQL Server 数据库中执行的项目的操作。 有关 GUI 提供的 SQL 适配器的详细信息，请参阅[浏览、 搜索和 get 元数据以执行 SQL 操作的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter.md)。  
  
## <a name="what-are-binding-properties-in-the-sql-adapter-where-can-i-find-information-about-all-the-binding-properties-in-sql-adapter"></a>什么 SQL 适配器中的绑定属性？ 在哪里可以找到 SQL 适配器中的绑定的所有属性的信息？  
 适配器客户端可以使用中的绑定属性[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]来配置和控制适配器的行为。 有关绑定的所有属性的信息显示在[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，请参阅[了解针对 SQL Server 适配器绑定属性的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sql/read-about-the-biztalk-adapter-for-sql-server-adapter-binding-properties.md)。  
  
## <a name="what-is-msdtc-do-i-need-to-bother-about-it-before-using-sql-adapter"></a>什么是 MSDTC？ 是否需要使用 SQL 适配器之前涉及有关它？  
 MSDTC 代表 Microsoft 分布式事务处理协调器。 MSDTC 协调多个资源管理器，如数据库、 文件系统和消息队列之间的各种事务。 若要使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，必须启用 MSDTC。 有关配置 MSDTC 的详细信息，请参阅[配置 SQL Server 和适配器客户端上的 MSDTC](../../adapters-and-accelerators/adapter-sql/configure-msdtc-on-sql-server-and-adapter-client.md)。  
  
## <a name="where-can-i-find-information-about-the-sql-server-data-types-that-are-supported-in-the-sql-adapter"></a>在哪里可以找到有关 SQL 适配器中支持的 SQL Server 数据类型的信息？  
 若要了解的有关 SQL 适配器中支持的 SQL Server 数据类型，请参阅[基本 SQL Server 数据类型](../../adapters-and-accelerators/adapter-sql/basic-sql-server-data-types.md)。  
  
## <a name="which-approach-biztalk-server-wcf-service-model-or-wcf-channel-model-can-i-use-to-perform-various-operations-using-the-sql-adapter"></a>我可使用哪种方法 （BizTalk Server、 WCF 服务模型或 WCF 通道模型） 来执行各种操作使用的 SQL 适配器？  
 若要了解可用于执行各种操作使用的 SQL 适配器的方法，请参阅[开发 SQL 应用程序](../../adapters-and-accelerators/adapter-sql/develop-your-sql-applications.md)。  
  
 
## <a name="see-also"></a>另请参阅  
 [常见问题](../../adapters-and-accelerators/frequently-asked-questions-for-the-biztalk-adapter-pack.md)
 