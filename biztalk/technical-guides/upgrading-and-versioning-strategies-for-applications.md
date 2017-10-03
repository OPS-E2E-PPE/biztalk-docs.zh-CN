---
title: "升级和应用程序的版本控制策略 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e881def2-c407-4205-a6b3-5c1fa5144bb4
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6763cb76cb0471d56a31e88ff95acea439bff077
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="upgrading-and-versioning-strategies-for-applications"></a>升级和应用程序的版本控制策略
BizTalk 应用程序版本控制可以成为一个问题，当您需要同时运行两个版本的 BizTalk 解决方案由并行，或者如果你不能用于 BizTalk 应用程序停机时间部署的新版本。 如果不需要运行两个版本的同时 （例如，你有任何长时间运行业务流程），该解决方案和服务维护时段都可用，它是完全可以接受，若要取消部署的旧版本，并将其部署新的版本作为版本控制策略 （没有程序集版本控制）。 这是可能的版本控制策略，但我们仍建议使用文件的版本号递增 (若要让你知道哪个版本部署在运行的计算机上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)])。  
  
## <a name="when-to-use-versioning"></a>何时使用版本控制  
 如果你需要支持长时间运行业务流程和/或你需要执行 BizTalk 应用程序部署与 BizTalk 应用程序停机时间，则你需要实现和做法可靠，端到端[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]版本控制策略不同的版本控制方案。 这包括.NET 程序集版本控制和所有 BizTalk 项目，其中包括架构、 地图、 管道、 管道组件、 业务流程、 自定义适配器的版本控制、 自定义类中被调用的业务流程和图、 业务规则和 BAM。  
  
 架构版本控制中是唯一的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管道确定目标命名空间加上根节点上基于消息的消息类型的架构中定义的名称。 有关详细信息，请参阅[管道组件中的架构解析](http://go.microsoft.com/fwlink/?LinkId=154207)(http://go.microsoft.com/fwlink/?LinkId=154207)。 如果你需要版本你的架构，版本指示器必须是目标命名空间的一部分。 更改架构版本在整个解决方案，产生连锁反应，因此应事先计划。 在创建业务流程消息时，请遵循 MSDN 杂志文章中的建议[BizTalk Server： 的更好的 BizTalk 编程 8 提示和技巧](http://go.microsoft.com/fwlink/?LinkId=101594)，提示 #1:"始终使用多部分消息类型"(http://go.microsoft.com/fwlink/？LinkId = 101594)。 使用此方法提供更大的灵活性时版本控制架构。  
  
## <a name="using-factoring-for-assembly-versioning"></a>使用分解的程序集版本控制  
 如果你需要支持长时间运行业务流程、-并排部署或无停机升级，，则应实现的程序集版本控制和打包策略。 若要执行的 BizTalk 项目的程序集版本控制，BizTalk 解决方案程序集需要包含 （打包） 的方式以允许[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]版本控制。  有三种类型的分解：  
  
-   **没有将分解**  
  
     BizTalk 中的所有项目都都在一个程序集中。 这是最容易了解和部署，但可以最大的灵活性。  
  
-   **完整将分解**  
  
     每个 BizTalk 项目位于其自己的程序集中。 这提供了最大的灵活性，但最复杂部署并了解。  
  
-   **最佳将分解**  
  
     某个位置之间"没有将分解"和"完整将分解"会基于 BizTalk 应用程序的深入分析。 除了版本控制，这允许你轻松地实现你的 BizTalk 主机设计。 这被通过寻找 BizTalk 项目之间的关系。 通常情况下可以位于同一程序集中将一起始终是已进行版本管理的项目。 如果需要的项目的独立版本控制，然后必须将它们置于不同的程序集中。 这是级别您想要获得分解。  
  
## <a name="additional-resources"></a>其他资源  
 有关实现和优化最佳做法的详细信息请参阅[MSDN 网络广播： 实现和优化 BizTalk Server 解决方案最佳做法](http://go.microsoft.com/fwlink/?LinkId=101595)(http://go.microsoft.com/fwlink/?LinkId=101595)。  
  
 定义和做法稳定版本控制策略以确保它提供了你可能需要任何通过并行部署策略。 BizTalk Server 应用程序升级和版本控制策略的资源包括：  
  
-   [更新应用程序](../technical-guides/updating-an-application.md)  
  
-   [更新 BizTalk 应用程序](http://go.microsoft.com/fwlink/?LinkId=154208)(http://go.microsoft.com/fwlink/?LinkId=154208) 和子主题。  
  
-   [BizTalk Server 项目版本控制](http://go.microsoft.com/fwlink/?LinkId=154209)(http://go.microsoft.com/fwlink/?LinkId=154209)  
  
-   [了解 BizTalk Server 应用程序部署](http://go.microsoft.com/fwlink/?LinkId=101599)(http://go.microsoft.com/fwlink/?LinkId=101599)  
  
-   [BizTalk Server 2006-管道组件的并行部署](http://go.microsoft.com/fwlink/?LinkId=101600)(http://go.microsoft.com/fwlink/?LinkId=101600)  
  
-   [BizTalk Server 2006 生命周期简短的视频演示说明](http://go.microsoft.com/fwlink/?LinkId=101601)(http://go.microsoft.com/fwlink/?LinkId=101601)  
  
> [!NOTE]  
>  即使这些文章的一些专门为编写[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]，其内容也适用于[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]。  
  
## <a name="see-also"></a>另请参阅  
 [清单： 配置 BizTalk Server](../technical-guides/checklist-configuring-biztalk-server.md)