---
title: 教程：将 BizTalk 项目迁移到 Oracle 数据库适配器 |Microsoft Docs
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
ms.openlocfilehash: 1aca70228a53e88ab143820e3a6bf07409844392
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65375890"
---
# <a name="tutorial-migrate-biztalk-projects-to-the-oracle-database-adapter"></a>教程：将 BizTalk 项目迁移到 Oracle 数据库适配器
用于与 Microsoft BizTalk Server 附带的 Oracle 数据库的 BizTalk ODBC 适配器不同于基于 WCF 的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在许多方面，包括：  
  
- 创建 BizTalk 项目的设计时体验。  
  
- 元数据检索体验。  
  
- 架构文件的名称和命名空间。  
  
- 数据类型映射。  
  
- 可以使用适配器执行的操作。  
  
- 在 BizTalk Server 管理控制台中的物理端口配置  
  
  在中的主题解释了这些差异[迁移 BizTalk 项目创建使用 Oracle 数据库的 BizTalk ODBC 适配器](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e)。  
  
  但是，可以使用用于 Oracle 数据库的 BizTalk ODBC 适配器创建的 BizTalk 项目进行更改并使其适用于基于 WCF 的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
  本教程将说明了对创建 BizTalk ODBC 适配器将用于 Oracle 数据库的现有 BizTalk 项目应做的更改。  
  
> [!NOTE]
>  在本教程中，为了简洁起见，用于 Oracle 数据库的 BizTalk ODBC 适配器将称为"vPrev Oracle 数据库适配器"。 同样，使用 vPrev Oracle 数据库适配器的 BizTalk 项目会被称为"vPrev BizTalk 项目。  
  
## <a name="sample-used-for-the-tutorial"></a>本教程使用示例  
 基于本教程演示如何迁移 vPrev BizTalk 项目的示例 (Oracle_Migration)。 与 Microsoft 提供了示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。 有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。  
  
## <a name="prerequisites"></a>先决条件  
  
- 必须有一个 vPrev BizTalk 项目。 本教程涉及到执行插入操作客户表上的 BizTalk 项目。 通过运行提供的 SQL 脚本在 SCOTT 架构下创建客户表[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]示例。  
  
- 您必须具有要执行使用 vPrev Oracle 数据库适配器对 Oracle 数据库插入操作的请求消息。 请求消息必须符合使用 vPrev Oracle 数据库适配器生成的插入操作的架构。  
  
- 你必须完成中的步骤[先决条件](../../adapters-and-accelerators/adapter-oracle-database/prerequisites-to-create-oracle-database-applications.md) 
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>了解 BizTalk 项目创建使用以前版本的适配器  
 创建的 vPrev BizTalk 项目的关键组成部分包括：  
  
- **BizTalk 业务流程**。 这是一个简单的业务流程提取请求消息从一个文件位置，将发送到使用 Oracle 的 Oracle 数据库的请求消息发送接收端口、 接收响应，并将其保存到另一个文件位置。  
  
- **您想要对 Oracle 数据库执行的操作架构**。 本教程涉及 SCOTT 架构中执行插入操作的客户表上的 BizTalk 项目。 通过运行提供的 SQL 脚本在 SCOTT 架构下创建客户表[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]示例。 生成的 CUSTOMER 表的架构是 CUSTOMERService_CUSTOMER_x5d.xsd。 此架构是使用 vPrev Oracle 数据库适配器生成的。  
  
  > [!NOTE]
  >  与基于 WCF 的不同[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，vPrev Oracle 数据库适配器不支持 Oracle 数据库表上的特定操作生成的元数据。 默认情况下，适配器生成的表支持的所有操作的架构。 有关 vPrev Oracle 数据库适配器和基于 WCF 的更多此类差异[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[迁移 BizTalk 项目创建使用 Oracle 数据库的 BizTalk ODBC 适配器](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e)。  
  
- **请求消息**。 要执行客户表上的插入操作的请求消息。 显示以前版本的 Oracle 数据库适配器插入操作的架构符合请求消息的架构。  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a>使用以前版本的适配器如何迁移 BizTalk 项目创建  
 此迁移教程的目的是使您能够将请求消息，符合架构生成 vPrev Oracle 数据库适配器，使用可以只处理符合基于 WCF 的消息的 WCF 自定义端口的发送[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。 因此，简单地说，迁移活动包括： 配置 WCF 自定义端口来处理消息的不符合基于 WCF 的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]的架构。  
  
 但是，若要能够适当地配置 WCF 自定义端口，必须执行以下任务：  
  
- 生成 SCOTT 上的插入操作的元数据。使用基于 WCF 的 CUSTOMER 表[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
- 执行插入操作执行 Insert 操作使用基于 WCF 的使用 vPrev Oracle 数据库适配器添加到请求消息的请求消息映射[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  
- 使用基于 WCF 的接收响应消息映射[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]到 vPrev Oracle 数据库适配器的响应消息。  
  
- 创建 WCF 自定义 Oracle 发送接收端口在 BizTalk Server 管理控制台。  
  
- 配置要使用的请求和响应的映射的 WCF 自定义端口。  
  
 
  
## <a name="see-also"></a>请参阅  
[Biztalk Server 入门](../../core/getting-started-with-biztalk-server.md)