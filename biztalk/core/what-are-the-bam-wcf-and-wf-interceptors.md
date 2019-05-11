---
title: 什么是 BAM WCF 和 WF 侦听器？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 198bfdc9-86ff-4017-b65f-19616deeb9f4
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3cfa81307220a2685768e2ac13d1a4c922cf944
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244114"
---
# <a name="what-are-the-bam-wcf-and-wf-interceptors"></a>什么是 BAM WCF 和 WF 侦听器？
业务活动监视 (BAM) 是一系列工具、 Api 和服务，可用于管理聚合、 警报和配置文件，以及提供实现自动化的过程来发送事件来监视相关业务度量。 在一起，这些提供端到端可见性，业务流程，让大家随时了解业务流程状态和结果。  
  
 BAM 侦听器将扩展到 Windows Workflow Foundation (WF)、 Windows Communication Foundation (WCF) 和其他运行时环境这一功能。 通过使用 BAM 侦听器，可以跟踪业务流程，无需重新编译 WF 或 WCF 解决方案，集成通过配置文件实现。  
  
 通过在项目中使用 BAM WF 或 WCF 侦听器，你可以：  
  
-   使用 BAM 门户查看有关 WF 或 WCF 应用程序中运行的业务流程的信息。  
  
-   使用 BAM 功能而无需额外的代码添加到你的应用程序。  
  
-   部署解决方案是使用熟悉的 BizTalk Server 工具和实用程序。  
  
-   利用现有 BizTalk Server 环境的现有和新 WF 和 WCF 应用程序。  
  
## <a name="interceptor-components"></a>侦听器组件  
 每个 BAM 侦听器的核心是公用侦听器基础的一组用于构建针对异类环境的自定义侦听器奠定了基础的组件。 公用侦听器基础包含下列共享的组件：  
  
-   **bm.exe**，BAM 部署实用工具的增强的版本扩展，用于修改侦听器配置，包括添加、 删除、 更新和列表的功能。  
  
-   **CommonInterceptorConfiguration.xsd**，公用侦听器基础配置 XML 架构。 最小值，必须根据此架构验证所有侦听器配置。  
  
## <a name="windows-workflow-foundation-wf-interceptor"></a>Windows Workflow Foundation (WF) 侦听器  
 Windows Workflow Foundation 侦听器可以以透明方式添加 BAM 跟踪到新的和现有 WF 应用程序的功能。 在将侦听器配置已部署到 BAM 主导入数据库和 WF 应用程序的每个实例已配置为加载 BAM WF 侦听器，则工作流数据将写入到 BAM，无额外代码。 WF 侦听器提供下列功能：  
  
-   插入到现有 WF 应用程序，而无需更改代码或重新编译。  
  
-   启用运行时检测和支持的更改的配置文件。 如果检测到的侦听器配置文件的新版本，则新工作流实例将使用新配置，而旧工作流实例将使用旧的配置完成。  
  
-   支持事务。 WF 侦听器事务上一致的方式与 WF 事务保留跟踪的项。 当 WF 事务和侦听器事务成功完成时，才会保留跟踪的项。  
  
    > [!NOTE]
    >  Windows Workflow 侦听器不支持 SharedConnectionWorkflowCommitWorkBatchService，后者跟踪和持久性服务使用相同的 SQL 连接。  
  
    > [!NOTE]
    >  在 BizTalk Server 中，Windows Workflow Foundation (WF) 侦听器会不会与.NET Framework 4 中的新 WF 引擎协同工作。 WF 侦听器会继续在.NET Framework 3.5 SP2 中工作。  
  
## <a name="windows-communication-foundation-wcf-interceptor"></a>Windows Communication Foundation (WCF) 侦听器  
 Windows Communication Foundation 侦听器提供 BAM 跟踪对 WCF 应用程序的功能。 它提供以下功能：  
  
-   插入到现有 WCF 应用程序，而无需更改代码或重新编译。  
  
-   跟踪 WCF 服务调用中包含的消息。  
  
-   从 WCF 服务调用中的消息跟踪的信息。  
  
-   参与事务从客户端流入或在内部启动针对事务的服务调用。