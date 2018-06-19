---
title: 教程： 将 BizTalk 项目迁移到 Oracle 数据库适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a393219-bae8-4e08-acc8-76986600d0de
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0948e79b7f236bb20bbff9101195809bcc921a68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215341"
---
# <a name="tutorial-migrate-biztalk-projects-to-the-oracle-database-adapter"></a>教程： 将 BizTalk 项目迁移到 Oracle 数据库适配器
包含 Microsoft BizTalk Server 提供的 Oracle Database BizTalk ODBC 适配器不同于基于 WCF 的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在许多方面，包括：  
  
-   创建 BizTalk 项目的设计时体验。  
  
-   元数据检索体验。  
  
-   架构文件名称和命名空间。  
  
-   数据类型映射。  
  
-   可以使用该适配器执行的操作。  
  
-   在 BizTalk Server 管理控制台中的物理端口配置  
  
 在中的主题解释了这些差异[迁移 BizTalk 项目创建使用 Oracle 数据库的 BizTalk ODBC 适配器](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e)。  
  
 但是，你可以使用用于 Oracle 数据库的 BizTalk ODBC 适配器已创建 BizTalk 项目进行更改，并使其适用于基于 WCF 的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
 本教程将说明了你应使用用于 Oracle 数据库的 BizTalk ODBC 适配器创建的现有 BizTalk 项目进行的更改。  
  
> [!NOTE]
>  在本教程中，由于篇幅所限，Oracle 数据库 BizTalk ODBC 适配器将被称为"vPrev Oracle 数据库适配器"。 同样，使用 vPrev Oracle 数据库适配器的 BizTalk 项目将称为"vPrev BizTalk 项目"。  
  
## <a name="sample-used-for-the-tutorial"></a>使用本教程的示例  
 本教程基于演示如何将 vPrev BizTalk 项目迁移的示例 (Oracle_Migration)。 与 Microsoft 提供了示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="prerequisites"></a>先决条件  
  
-   你必须有 vPrev BizTalk 项目。 本教程涉及 BizTalk 项目执行对 CUSTOMER 表的插入操作。 通过运行提供的 SQL 脚本在 SCOTT 架构下创建客户表[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]示例。  
  
-   你必须具有要执行插入操作使用 vPrev Oracle 数据库适配器对 Oracle 数据库的请求消息。 请求消息必须符合使用 vPrev Oracle 数据库适配器所生成的 Insert 操作的架构。  
  
-   你必须已完成中的步骤[先决条件](../../adapters-and-accelerators/adapter-oracle-database/prerequisites-to-create-oracle-database-applications.md) 
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>了解 BizTalk 项目创建使用以前的版本的适配器  
 VPrev BizTalk 项目创建的关键组成部分是：  
  
-   **BizTalk 业务流程**。 这是简单的业务流程选取端口的文件位置，发送到使用 Oracle 的 Oracle 数据库的请求消息发送接收的请求消息、 接收响应，并将其保存到另一个文件位置。  
  
-   **你想要对 Oracle 数据库执行的操作架构**。 本教程涉及 SCOTT 架构中执行插入操作 CUSTOMER 表中的 BizTalk 项目。 通过运行提供的 SQL 脚本在 SCOTT 架构下创建客户表[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]示例。 为客户表生成的架构是 CUSTOMERService_CUSTOMER_x5d.xsd。 使用 vPrev Oracle 数据库适配器生成此架构。  
  
    > [!NOTE]
    >  与不同的是基于 WCF 的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，vPrev Oracle 数据库适配器不支持 Oracle 数据库表上的特定操作生成的元数据。 默认情况下，适配器生成架构的表支持的所有操作。 多此类之间的差异 vPrev Oracle 数据库适配器和基于 WCF 的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[迁移 BizTalk 项目创建使用 Oracle 数据库的 BizTalk ODBC 适配器](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e)。  
  
-   **请求消息**。 要执行对 CUSTOMER 表的插入操作的请求消息。 请求消息的架构符合插入操作的架构，如以前版本的 Oracle 数据库适配器显示。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>如何迁移 BizTalk 项目创建使用以前的版本的适配器  
 本教程中迁移的目标是使你可以发送请求消息，符合架构生成的 vPrev Oracle 数据库适配器，使用只能处理符合基于 WCF 的消息的 WCF 自定义端口[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 因此，简单地说，迁移练习涉及配置基于 WCF 的不符合的处理消息的 WCF 自定义端口[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]的架构。  
  
 但是，若要能够相应地配置 WCF 自定义端口，必须执行以下任务：  
  
-   生成 SCOTT 上的插入操作的元数据。使用基于 WCF 的 CUSTOMER 表[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
-   用于执行插入操作执行使用基于 WCF 的插入操作使用请求消息的 vPrev Oracle 数据库适配器将请求消息映射[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
-   将使用基于 WCF 的接收响应消息映射[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]到 vPrev Oracle 数据库适配器的响应消息。  
  
-   创建 WCF 自定义 Oracle 发送接收 BizTalk Server 管理控制台中的端口。  
  
-   配置要使用的请求和响应的映射的 WCF 自定义端口。  
  
 
  
## <a name="see-also"></a>另请参阅  
[Biztalk Server 入门](../../core/getting-started-with-biztalk-server.md)