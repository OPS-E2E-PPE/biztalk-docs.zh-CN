---
title: 教程 2： 迁移 BizTalk 项目中 Siebel |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a2a1828-8cc8-4b80-99bd-c083c04e5d04
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b8d138d348e750102d82a4aba2e39bc7d119c8c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223005"
---
# <a name="tutorial-2-migrating-biztalk-projects-in-siebel"></a>教程 2： 迁移中 Siebel 的 BizTalk 项目
Microsoft BizTalk 服务器随附的 Siebel 适配器以前版本的基于 WCF 的不同[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]在许多方面，包括：  
  
-   创建 BizTalk 项目的设计时体验。  
  
-   元数据检索体验。  
  
-   架构文件名称和命名空间。  
  
-   数据类型映射。  
  
-   可以使用该适配器执行的操作。  
  
-   在 BizTalk Server 管理控制台中的物理端口配置  
  
 在中的主题解释了这些差异[迁移 BizTalk 项目创建使用 Siebel 适配器的上一步版本](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e)。  
  
 但是，你可以使用以前版本的适配器创建 BizTalk 项目进行更改，并使其适用于基于 WCF 的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
 本教程将说明了你应创建使用以前的版本的适配器的现有 BizTalk 项目的更改。  
  
> [!NOTE]
>  在本教程中，由于篇幅所限，以前版本的 Siebel 适配器称为 vPrev Siebel 适配器。 同样，使用 vPrev Siebel 适配器的 BizTalk 项目将被称为 vPrev BizTalk 项目。  
  
## <a name="sample-used-for-the-tutorial"></a>使用本教程的示例  
 本教程基于演示如何将执行插入操作帐户 Siebel 业务组件上的 vPrev BizTalk 项目迁移的示例 (Siebel_BussComp_Migration)。 与 Microsoft 提供了示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="prerequisites"></a>先决条件  
  
-   你必须有 vPrev BizTalk 项目。 本教程涉及执行插入操作帐户在业务组件上的 BizTalk 项目。  
  
-   你必须具有要执行插入操作帐户在业务组件使用 vPrev Siebel 适配器上的请求消息。 请求消息必须符合使用 vPrev Siebel 适配器所生成的 Insert 操作的架构。  
  
-   你必须已完成中的步骤[创建 Siebel 应用程序的先决条件](../../adapters-and-accelerators/adapter-siebel/prerequisites-to-create-siebel-applications.md)。  
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>了解 BizTalk 项目创建使用以前的版本的适配器  
 VPrev BizTalk 项目创建的关键组成部分是：  
  
-   **BizTalk 业务流程**。 这是简单的业务流程选取端口的文件位置，发送到 Siebel 系统使用 Siebel 请求消息发送接收的请求消息、 接收响应，并将其保存到另一个文件位置。  
  
-   **你想要在 Siebel 在业务组件上执行的操作的架构**。 本教程涉及执行插入操作帐户在业务组件上的 BizTalk 项目。 为帐户在业务组件生成的架构是 AccountService_Account_x5d.xsd。 使用 vPrev Siebel 适配器生成此架构。  
  
    > [!NOTE]
    >  与不同的是基于 WCF 的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，vPrev Siebel 适配器不支持在业务组件上的特定操作生成的元数据。 默认情况下，适配器生成的业务组件支持的所有操作的架构。 多此类之间的差异 vPrev Siebel 适配器和基于 WCF 的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[迁移 BizTalk 项目创建使用 Siebel 适配器的上一步版本](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e)。  
  
-   **请求消息**。 要执行插入操作帐户在业务组件上的请求消息。 请求消息的架构符合插入操作的架构，如显示 vPrev Siebel 适配器。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>如何迁移 BizTalk 项目创建使用以前的版本的适配器  
 本教程中迁移的目标是使您能够发送请求消息符合架构生成的使用只能处理符合基于 WCF 的消息的 WCF 自定义端口和 vPrev Siebel 适配器[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 因此，简单地说，迁移练习涉及配置基于 WCF 的不符合的处理消息的 WCF 自定义端口[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]的架构。  
  
 但是，若要能够相应地配置 WCF 自定义端口，必须执行以下任务：  
  
-   生成使用基于 WCF 的帐户在业务组件上的插入操作的元数据[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
-   用于执行插入操作执行使用基于 WCF 的插入操作使用请求消息的 vPrev Siebel 适配器将请求消息映射[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
-   将使用基于 WCF 的接收响应消息映射[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]到 vPrev Siebel 适配器的响应消息。  
  
-   创建 WCF 自定义 Siebel 发送接收 BizTalk Server 管理控制台中的端口。  
  
-   配置要使用的请求和响应的映射的 WCF 自定义端口。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1： 修改 vPrev Oracle 数据库中的 BizTalk 项目](../../adapters-and-accelerators/adapter-oracle-database/step-1-modify-the-vprev-biztalk-project-in-oracle-database.md)  
  
-   [步骤 2： 在 BizTalk Server 管理控制台，以使用 ORacle 数据库适配器中配置业务流程](../../adapters-and-accelerators/adapter-oracle-database/step-2-configure-an-orchestration-to-use-the-oracle-db-adapter-in-biztalk.md)  
  
-   [步骤 3： 测试与 Siebel 适配器迁移应用程序](../../adapters-and-accelerators/adapter-siebel/step-3-test-the-migrated-application-with-the-siebel-adapter.md)  
  
## <a name="see-also"></a>另请参阅  
 [Siebel 适配器教程](../../adapters-and-accelerators/adapter-siebel/siebel-adapter-tutorials.md)