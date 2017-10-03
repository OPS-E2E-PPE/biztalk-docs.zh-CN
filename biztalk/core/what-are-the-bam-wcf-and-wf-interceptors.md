---
title: "什么是 BAM WCF 和 WF 侦听器？ | Microsoft Docs"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 198bfdc9-86ff-4017-b65f-19616deeb9f4
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c819d219a9796b485434101ee1c2f2d4be136ae0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-are-the-bam-wcf-and-wf-interceptors"></a>什么是 BAM WCF 和 WF 侦听器？
业务活动监视 (BAM) 是一个由工具、API 和服务组成的集合，用于管理聚合、警报和配置文件，以及提供实现自动发送事件流程所需的工具，以监视相关业务度量。 同时，还实现了对业务流程的端对端查看，使你可以了解业务流程的最新状态和结果。  
  
 BAM 侦听器将这一功能扩展到 Windows Workflow Foundation (WF)、Windows Communication Foundation (WCF) 以及其他运行时环境中。 使用 BAM 侦听器，你无需重新编译 WF 或 WCF 解决方案即可跟踪业务流程，因为集成是通过配置文件实现的。  
  
 通过在项目中使用 BAM WF 或 WCF 侦听器，你可以执行下列操作：  
  
-   使用 BAM 门户查看有关在 WF 或 WCF 应用程序中运行的业务流程的信息。  
  
-   在无需向应用程序添加额外代码的情况下使用 BAM 功能。  
  
-   使用你熟悉的 BizTalk Server 工具和实用工具部署解决方案。  
  
-   利用现有 BizTalk Server 环境改进现有和新增的 WF 和 WCF 应用程序。  
  
## <a name="interceptor-components"></a>侦听器组件  
 每个 BAM 侦听器的核心是公用侦听器基础，公用侦听器基础是一个组件集，为构建用于异构环境的自定义侦听器奠定了基础。 公用侦听器基础包含下列共享组件：  
  
-   **bm.exe**，BAM 部署实用工具的增强的版本扩展以修改侦听器配置，包括添加、 删除、 更新和列表功能。  
  
-   **CommonInterceptorConfiguration.xsd**，常见的侦听器 Foundation 配置 XML 架构。 所有侦听器配置都必须至少根据此架构进行验证。  
  
## <a name="windows-workflow-foundation-wf-interceptor"></a>Windows Workflow Foundation (WF) 侦听器  
 通过 Windows Workflow Foundation 侦听器，你可以以透明方式向新增和现有 WF 应用程序添加 BAM 跟踪功能。 在将侦听器配置部署到 BAM 主导入数据库，并将 WF 应用程序的每个实例配置为加载 BAM WF 侦听器之后，工作流数据便会写入到 BAM，无需额外代码。 WF 侦听器提供下列功能：  
  
-   在不需要更改或重新编译代码的情况下插入到现有 WF 应用程序中。  
  
-   允许对已更改的配置文件进行运行时检测和支持。 如果检测到新版本的侦听器配置文件，新工作流实例将使用新配置，而旧工作流实例将完成对旧配置的使用。  
  
-   支持事务。 WF 侦听器以一种在事务性上与 WF 事务一致的方式来保留跟踪项。 仅当 WF 事务和侦听器事务成功完成时，才会保留跟踪项。  
  
    > [!NOTE]
    >  Windows Workflow 侦听器不支持 SharedConnectionWorkflowCommitWorkBatchService，后者对跟踪和持久性服务使用相同的 SQL 连接。  
  
    > [!NOTE]
    >  在 BizTalk Server 中 Windows Workflow Foundation (WF) 拦截器不会使用.NET Framework 4 中的新 WF 引擎。 WF 拦截器将继续在.NET Framework 3.5 SP2 中工作。  
  
## <a name="windows-communication-foundation-wcf-interceptor"></a>Windows Communication Foundation (WCF) 侦听器  
 Windows Communication Foundation 侦听器向 WCF 应用程序提供 BAM 跟踪功能， 它提供以下功能：  
  
-   在不需要更改或重新编译代码的情况下插入到现有 WCF 应用程序。  
  
-   跟踪 WCF 服务调用中包含的消息。  
  
-   跟踪 WCF 服务调用中各消息中的信息。  
  
-   参与从客户端流入的事务或针对事务服务调用从内部启动的事务。