---
title: 教程 2： 迁移 BizTalk 项目中 Siebel |Microsoft Docs
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
ms.openlocfilehash: 3ada19454c3d2aef1c725987d8d37f7b98a2d1c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996430"
---
# <a name="tutorial-2-migrating-biztalk-projects-in-siebel"></a>教程 2： 迁移中 Siebel 的 BizTalk 项目
Siebel 适配器随 Microsoft BizTalk Server 的以前版本不同于基于 WCF 的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]在许多方面，包括：  
  
- 创建 BizTalk 项目的设计时体验。  
  
- 元数据检索体验。  
  
- 架构文件的名称和命名空间。  
  
- 数据类型映射。  
  
- 可以使用适配器执行的操作。  
  
- 在 BizTalk Server 管理控制台中的物理端口配置  
  
  在中的主题解释了这些差异[迁移 BizTalk 项目创建使用 Siebel 适配器的上一步版本](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e)。  
  
  但是，可以创建使用以前版本的适配器的 BizTalk 项目进行更改并使其适用于基于 WCF 的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
  本教程说明了您应该对使用以前版本的适配器创建的现有 BizTalk 项目的更改。  
  
> [!NOTE]
>  本教程中，为了简洁起见，在以前版本的 Siebel 适配器称为 vPrev Siebel 适配器。 同样，使用 vPrev Siebel 适配器的 BizTalk 项目将引用为 vPrev BizTalk 项目。  
  
## <a name="sample-used-for-the-tutorial"></a>本教程使用示例  
 基于本教程演示如何迁移执行插入操作帐户 Siebel 业务组件上的 vPrev BizTalk 项目的示例 (Siebel_BussComp_Migration)。 与 Microsoft 提供了示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="prerequisites"></a>必要條件  
  
-   必须有一个 vPrev BizTalk 项目。 本教程涉及到执行插入操作帐户业务组件上的 BizTalk 项目。  
  
-   您必须具有要执行插入操作帐户业务组件使用 vPrev Siebel 适配器上的请求消息。 请求消息必须符合使用 vPrev Siebel 适配器生成的插入操作的架构。  
  
-   你必须完成中的步骤[创建 Siebel 应用程序的先决条件](../../adapters-and-accelerators/adapter-siebel/prerequisites-to-create-siebel-applications.md)。  
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>了解 BizTalk 项目创建使用以前版本的适配器  
 创建的 vPrev BizTalk 项目的关键组成部分包括：  
  
- **BizTalk 业务流程**。 这是一个简单的业务流程提取请求消息从一个文件位置，将发送到使用 Siebel 的 Siebel 系统的请求消息发送接收端口、 接收响应，并将其保存到另一个文件位置。  
  
- **你想要在 Siebel 业务组件上执行的操作架构**。 本教程涉及到执行插入操作帐户业务组件上的 BizTalk 项目。 为帐户业务组件生成的架构是 AccountService_Account_x5d.xsd。 此架构是使用 vPrev Siebel 适配器生成的。  
  
  > [!NOTE]
  >  与基于 WCF 的不同[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，vPrev Siebel 适配器不支持在业务组件上的特定操作生成的元数据。 默认情况下，适配器生成的在业务组件上受支持的所有操作的架构。 有关 vPrev Siebel 适配器和基于 WCF 的更多此类差异[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[迁移 BizTalk 项目创建使用 Siebel 适配器的上一步版本](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e)。  
  
- **请求消息**。 要执行插入操作帐户业务组件上的请求消息。 请求消息的架构符合插入操作的架构，如 vPrev Siebel 适配器提供的。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>使用以前版本的适配器如何迁移 BizTalk 项目创建  
 此迁移教程的目的是使您能够将请求消息，符合架构生成 vPrev Siebel 适配器，使用可以只处理符合基于 WCF 的消息的 WCF 自定义端口的发送[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。 因此，简单地说，迁移活动包括： 配置 WCF 自定义端口来处理消息的不符合基于 WCF 的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]的架构。  
  
 但是，若要能够适当地配置 WCF 自定义端口，必须执行以下任务：  
  
- 为使用基于 WCF 的帐户业务组件上的插入操作生成元数据[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
- 执行插入操作执行 Insert 操作使用基于 WCF 的使用 vPrev Siebel 适配器添加到请求消息的请求消息映射[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
- 使用基于 WCF 的接收响应消息映射[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]到 vPrev Siebel 适配器的响应消息。  
  
- 创建自定义 WCF 的 Siebel 发送接收端口在 BizTalk Server 管理控制台。  
  
- 配置要使用的请求和响应的映射的 WCF 自定义端口。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [步骤 1： 修改 vPrev BizTalk 项目中 Oracle 数据库](../../adapters-and-accelerators/adapter-oracle-database/step-1-modify-the-vprev-biztalk-project-in-oracle-database.md)  
  
-   [步骤 2： 配置业务流程在 BizTalk Server 管理控制台中使用 ORacle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/step-2-configure-an-orchestration-to-use-the-oracle-db-adapter-in-biztalk.md)  
  
-   [步骤 3： 测试具有 Siebel 适配器的迁移应用程序](../../adapters-and-accelerators/adapter-siebel/step-3-test-the-migrated-application-with-the-siebel-adapter.md)  
  
## <a name="see-also"></a>请参阅  
 [Siebel 适配器教程](../../adapters-and-accelerators/adapter-siebel/siebel-adapter-tutorials.md)