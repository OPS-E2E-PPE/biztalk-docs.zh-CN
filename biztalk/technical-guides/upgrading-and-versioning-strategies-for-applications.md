---
title: 升级和版本的应用程序策略 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e881def2-c407-4205-a6b3-5c1fa5144bb4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bdf9484d04ff895af42a3321d7ff44651c9bb26
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65261323"
---
# <a name="upgrading-and-versioning-strategies-for-applications"></a>升级和应用程序的版本控制策略
BizTalk 应用程序版本控制可能会成为问题，当您需要运行两个版本的 BizTalk 解决方案的并排方案，或者无法使用 BizTalk 应用程序停机时间来部署新版本。 如果不需要运行两个版本的同时 （例如，其中有任何长时间运行的业务流程），解决方案和服务维护时段是否可用，则它是完全可以接受要取消部署旧版本，并将其部署新版本作为版本控制策略 （无程序集版本控制）。 这是一种可能的版本控制策略，但我们仍建议使用的文件版本号递增 (若要让你知道是哪个版本部署在运行的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)])。  
  
## <a name="when-to-use-versioning"></a>何时使用版本控制  
 如果你需要支持长时间运行的业务流程，和/或需要执行任何 BizTalk 应用程序停机的情况下，BizTalk 应用程序部署，则需要实现和练习实线、 端到端[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]版本控制的策略不同的版本控制方案。 这包括.NET 程序集版本控制和版本控制所有 BizTalk 项目，其中包括架构、 映射、 管道、 管道组件、 业务流程、 自定义适配器、 自定义类中调用的业务流程和映射、 业务规则和 BAM。  
  
 架构版本控制中是唯一的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管道确定目标命名空间加上根节点上基于消息的消息类型在架构中定义的名称。 有关详细信息，请参阅[管道组件中的架构解析](../core/schema-resolution-in-pipeline-components.md)。 如果需要版本您的架构，版本指示器必须是目标命名空间的一部分。 更改架构版本产生波纹效果在你的解决方案，并因此应该事先计划。 在创建业务流程消息时，搜索**BizTalk Server:提高 BizTalk 编程的 8 提示和技巧**(提示 1:始终使用多部分消息类型）。 使用此方法提供了更大的灵活性时架构版本控制。  
  
## <a name="using-factoring-for-assembly-versioning"></a>使用分解为程序集版本控制  
 如果你需要支持长时间运行的业务流程、 通过并行部署或无需停机的升级，，则应实现的程序集版本控制和打包策略。 若要执行的 BizTalk 项目的程序集版本控制，您的 BizTalk 解决方案程序集需要考虑 （打包） 的方式以允许[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]版本控制。  有三种类型的组成要素：  
  
-   **没有分解**  
  
     所有 BizTalk 项目都是在一个程序集中。 这是最容易了解和部署，但可以最大的灵活性。  
  
-   **完整分解**  
  
     每个 BizTalk 项目是在自己的程序集。 这提供了最大的灵活性，但最复杂部署和了解。  
  
-   **最佳分解**  
  
     某处次"没有分解"和"完整分解"基础 BizTalk 应用程序的深入分析。 除了版本控制，这允许您轻松地实现您的 BizTalk 主机的设计。 这被通过查找 BizTalk 项目之间的关系。 通常情况下可以在同一程序集中将一起始终进行版本控制的项目。 如果需要独立的版本控制的项目，然后它们必须放入不同的程序集。 该级别为你想要实现的重构。  
  
## <a name="additional-resources"></a>其他资源  
  
 定义和练习 solid 版本控制策略，以确保它提供了可能需要任何通过并行部署策略。 BizTalk Server 应用程序升级和版本控制策略的资源包括：  
  
-   [更新应用程序](../technical-guides/updating-an-application.md)  
  
-   [更新 BizTalk 应用程序](../core/updating-biztalk-applications.md)
  
-   [BizTalk Server 项目版本控制](../core/biztalk-server-project-versioning.md)  
  
-   [了解 BizTalk Server 应用程序部署](../core/understanding-biztalk-application-deployment-and-management.md)


  
## <a name="see-also"></a>请参阅  
 [清单：配置 BizTalk Server](../technical-guides/checklist-configuring-biztalk-server.md)
