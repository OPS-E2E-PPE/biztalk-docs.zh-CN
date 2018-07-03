---
title: 教程 1： 迁移到 SQL 适配器的 BizTalk 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b4d2dbb-e37c-4d70-831f-3bdac3c28c97
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea64d98404d247a47e8cad8df421c81752fe63e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013302"
---
# <a name="tutorial-1-migrate-biztalk-projects-to-the-sql-adapter"></a>教程 1： 将 BizTalk 项目迁移到 SQL 适配器
以前版本的 SQL 适配器随 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]不同于基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在许多方面，包括：  
  
- 创建 BizTalk 项目的设计时体验。  
  
- 元数据检索体验。  
  
- 架构文件的名称和命名空间。  
  
- 数据类型映射。  
  
- 可以使用适配器执行的操作。  
  
- 在 BizTalk Server 管理控制台中的物理端口配置  
  
  迁移 BizTalk 项目创建使用 SQLadapter 前一个版本中的主题介绍了这些差异。  
  
  但是，可以使用以前版本的适配器创建的 BizTalk 项目进行更改并使其适用于基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
  本教程说明了您应该对使用以前版本的适配器创建的现有 BizTalk 项目的更改。  
  
> [!NOTE]
>  本教程中，为了简洁起见，在以前版本的 SQL 适配器称为 vPrev SQL 适配器。 同样，使用 vPrev SQL 适配器的 BizTalk 项目将引用为 vPrev BizTalk 项目。  
> 
> [!IMPORTANT]
>  本教程提供有关如何执行基本的 insert 操作上的 SQL Server 数据库表的 vPrev SQL 适配器 BizTalk 项目迁移指南。 本教程不涵盖所有可能的方案从 vPrev SQL 适配器迁移到新的基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 必须使用此迁移教程的基础，并相应修改，以进行与你现有的项目相关的更改。  
  
## <a name="sample-used-for-the-tutorial"></a>本教程使用示例  
 基于本教程演示如何迁移 vPrev BizTalk 项目的示例 (SQL_Migration)。 与 Microsoft 提供了示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅示例。  
  
## <a name="prerequisites"></a>必要條件  
  
-   必须有一个 vPrev BizTalk 项目。 本教程涉及 SQL Server 数据库中执行插入操作客户表上的 BizTalk 项目。 Customer 表具有以下设计：  
  
    |列名|Description|  
    |-----------------|-----------------|  
    |v_custid|主键，整数类型，标识字段|  
    |“属性”|nchar(10) 类型|  
  
-   您必须具有要执行插入操作使用 vPrev SQL 适配器在 SQL Server 数据库上的请求消息。 请求消息必须符合使用 vPrev SQL 适配器生成的插入操作的架构。  
  
-   您应当已完成中的步骤[之前在开发 BizTalk 应用程序](http://msdn.microsoft.com/library/3539741d-5266-43d4-9b7b-73e82f0ed4f6)。  
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>了解 BizTalk 项目创建使用以前版本的适配器  
 创建的 vPrev BizTalk 项目的关键组成部分包括：  
  
-   **BizTalk 业务流程**。 这是一个简单的业务流程提取请求消息从一个文件位置，将发送到使用 WCF 自定义 SQL Server 数据库的请求消息发送接收端口、 接收响应，并将其保存到另一个文件位置。  
  
-   **您想要在 SQL Server 数据库上执行的操作架构**。 本教程涉及到执行插入操作的客户表上的 BizTalk 项目。 生成的 Customer 表的架构是 InsertCustomerService.xsd。 此架构是使用 vPrev SQL 适配器生成的。  
  
-   **请求消息**。 要执行客户表上的插入操作的请求消息。 显示以前版本的 SQL 适配器插入操作的架构符合请求消息的架构。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>使用以前版本的适配器如何迁移 BizTalk 项目创建  
 此迁移教程的目的是使您能够将请求消息，符合架构生成 vPrev SQL 适配器，使用可以只处理符合基于 WCF 的消息的 WCF 自定义端口的发送[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 因此，简单地说，迁移活动包括： 配置 WCF 自定义端口来处理消息的不符合基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]的架构。  
  
 但是，若要能够适当地配置 WCF 自定义端口，必须执行以下任务：  
  
- 生成上使用基于 WCF 的 Customer 表的插入操作的元数据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
- 执行插入操作执行 Insert 操作使用基于 WCF 的使用 vPrev SQL 适配器添加到请求消息的请求消息映射[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
- 使用基于 WCF 的接收响应消息映射[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]到 vPrev SQL 适配器的响应消息。  
  
- 创建 WCF 自定义 SQL 发送接收端口中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
- 配置要使用的请求和响应的映射的 WCF 自定义端口。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1： 修改 vPrev BizTalk 项目使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter.md)  
  
-   [步骤 2： 使用 SQL 适配器的 BizTalk Server 管理控制台中配置业务流程](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md)  
  
-   [步骤 3： 测试迁移应用程序使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/step-3-test-the-migrated-application-that-uses-the-sql-adapter.md)  
  
## <a name="see-also"></a>请参阅  
 [SQL 适配器教程](../../adapters-and-accelerators/adapter-sql/sql-adapter-tutorials.md)