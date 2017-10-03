---
title: "教程 1： 将 BizTalk 项目迁移到 SQL 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b4d2dbb-e37c-4d70-831f-3bdac3c28c97
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ca17095841fb154be9ec34766a34f174414cd82
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-1-migrate-biztalk-projects-to-the-sql-adapter"></a>教程 1： 将 BizTalk 项目迁移到 SQL 适配器
以前版本的 SQL 适配器随 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]不同于基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在许多方面，包括：  
  
-   创建 BizTalk 项目的设计时体验。  
  
-   元数据检索体验。  
  
-   架构文件名称和命名空间。  
  
-   数据类型映射。  
  
-   可以使用该适配器执行的操作。  
  
-   在 BizTalk Server 管理控制台中的物理端口配置  
  
 在迁移 BizTalk 项目创建使用 SQLadapter 的上一个版本中的主题解释了这些差异。  
  
 但是，你可以使用以前版本的适配器已创建 BizTalk 项目进行更改，并使其适用于基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
 本教程将说明了你应创建使用以前的版本的适配器的现有 BizTalk 项目的更改。  
  
> [!NOTE]
>  在本教程中，由于篇幅所限，以前版本的 SQL 适配器称为 vPrev SQL 适配器。 同样，使用 vPrev SQL 适配器的 BizTalk 项目将被称为 vPrev BizTalk 项目。  
  
> [!IMPORTANT]
>  本教程提供有关如何将执行的 SQL Server 数据库表上的基本插入操作 vPrev SQL 适配器 BizTalk 项目迁移指南。 本教程不涉及从 vPrev SQL 适配器迁移到新的所有可能的方案基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 必须使用此迁移教程为基础，并相应地修改以使与你的现有项目相关的更改。  
  
## <a name="sample-used-for-the-tutorial"></a>使用本教程的示例  
 本教程基于演示如何将 vPrev BizTalk 项目迁移的示例 (SQL_Migration)。 与 Microsoft 提供了示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅示例。  
  
## <a name="prerequisites"></a>先决条件  
  
-   你必须有 vPrev BizTalk 项目。 本教程涉及 SQL Server 数据库中执行插入操作客户表上的 BizTalk 项目。 Customer 表具有以下设计：  
  
    |列名|Description|  
    |-----------------|-----------------|  
    |v_custid|主键，整数类型，标识字段|  
    |Name|nchar(10) 类型|  
  
-   你必须具有要执行插入操作使用 vPrev SQL 适配器的 SQL Server 数据库的请求消息。 请求消息必须符合使用 vPrev SQL 适配器所生成的 Insert 操作的架构。  
  
-   你应完成中的步骤[之前你开发 BizTalk 应用程序](http://msdn.microsoft.com/library/3539741d-5266-43d4-9b7b-73e82f0ed4f6)。  
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>了解 BizTalk 项目创建使用以前的版本的适配器  
 VPrev BizTalk 项目创建的关键组成部分是：  
  
-   **BizTalk 业务流程**。 这是简单的业务流程选取端口的文件位置，发送到使用 WCF 自定义 SQL Server 数据库的请求消息发送接收的请求消息、 接收响应，并将其保存到另一个文件位置。  
  
-   **你想要在 SQL Server 数据库上执行的操作的架构**。 本教程涉及执行插入操作 Customer 表中的 BizTalk 项目。 为客户表生成的架构是 InsertCustomerService.xsd。 使用 vPrev SQL 适配器生成此架构。  
  
-   **请求消息**。 要执行对 Customer 表的插入操作的请求消息。 请求消息的架构符合插入操作的架构，如显示以前版本的 SQL 适配器。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>如何迁移 BizTalk 项目创建使用以前的版本的适配器  
 本教程中迁移的目标是使你可以发送请求消息，符合架构生成的 vPrev SQL 适配器，使用只能处理符合基于 WCF 的消息的 WCF 自定义端口[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 因此，简单地说，迁移练习涉及配置基于 WCF 的不符合的处理消息的 WCF 自定义端口[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]的架构。  
  
 但是，若要能够相应地配置 WCF 自定义端口，必须执行以下任务：  
  
-   生成上使用基于 WCF 的 Customer 表的插入操作的元数据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
-   用于执行插入操作执行使用基于 WCF 的插入操作使用请求消息的 vPrev SQL 适配器将请求消息映射[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
-   将使用基于 WCF 的接收响应消息映射[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]到 vPrev SQL 适配器的响应消息。  
  
-   创建 WCF 自定义 SQL 发送接收中的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
-   配置要使用的请求和响应的映射的 WCF 自定义端口。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1： 修改 vPrev BizTalk 项目使用的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter.md)  
  
-   [步骤 2： 在 BizTalk Server 管理控制台中使用的 SQL 适配器配置业务流程](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md)  
  
-   [步骤 3： 测试迁移使用的应用程序的 SQL 适配器](../../adapters-and-accelerators/adapter-sql/step-3-test-the-migrated-application-that-uses-the-sql-adapter.md)  
  
## <a name="see-also"></a>另请参阅  
 [SQL 适配器教程](../../adapters-and-accelerators/adapter-sql/sql-adapter-tutorials.md)