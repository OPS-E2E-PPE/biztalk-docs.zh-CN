---
title: 构建基块创建带有 Siebel 适配器 BizTalk 应用程序 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developing BizTalk applicatons, run-time tasks
- developing BizTalk applications, design-time tasks
ms.assetid: 76204181-18ad-43b5-b589-539aafd66835
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dea8fc354c3187ef7613ac35850b9408a05a9c0e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222589"
---
# <a name="building-blocks-to-create-biztalk-applications-with-the-siebel-adapter"></a>构建基块创建带有 Siebel 适配器 BizTalk 应用程序
执行操作 Siebel 系统使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]涉及两个组的活动： 设计时活动和运行时活动。 若要通过使用执行 Siebel 系统上的操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，必须执行一组使用的设计时和运行时任务[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]分别管理控制台。 本部分概述了这些任务。 本部分中，用于演示如何执行特定操作 Siebel 系统使用的所有主题[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，这些高级任务进行建模。  
  
## <a name="design-time-tasks"></a>设计时任务  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供能够浏览、 搜索和检索业务组件和业务服务中使用的 XML 架构定义语言 (Xsd) 形式的 Siebel 元数据[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 Xsd 是特定于你想要在 Siebel 系统上执行的操作和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]是仅当你创建 BizTalk 项目时，才可用。 在设计时可能需要执行以下任务。  
  
-   **创建 BizTalk 项目，并生成架构**。 开始时，你必须在 Microsoft 中创建 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]并生成业务组件或将调用 Siebel 系统中的业务服务的架构。 例如，如果你想要将一个记录插入帐户在业务组件，你必须生成插入操作的帐户在业务组件的元的数据。 在此步骤中，你将使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成架构。 有关详细信息，请参阅[获取 Visual Studio 中的 Siebel 操作的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)。  
  
-   **设置业务流程**。 一旦你已生成架构，必须通过使用 Orchestration 设计器来设置业务流程。 适用于基本的业务流程，你将添加发送和接收形状以及发送和接收逻辑端口。 在更高版本的步骤中，你将这些逻辑端口映射到的物理端口，使用 BizTalk Server 管理控制台。 业务流程使用这些端口以拾取适配器客户端发送的消息。 然后，业务流程将消息传递到 Siebel 系统。 一旦从 Siebel 系统收到的响应，业务流程将传递对适配器客户端的响应。  
  
-   **创建消息并将链接到架构**。 在您的业务流程，你必须创建将映射到第一步中生成的架构的消息。 通常情况下，你将创建请求和响应消息。 这些消息映射到相应的请求和响应架构。  
  
-   **将消息形状映射到消息和端口**。 在您的业务流程，现在必须映射到第三个步骤中创建的消息的第二步中添加每个形状。 你还必须将消息形状映射到该消息将发送在其的端口。  
  
     例如，如果您的业务流程中的第一个形状，将收到一条消息的接收形状将映射此形状，到"请求"消息和将请求消息发送的端口。  
  
-   **生成并部署 BizTalk 项目**。 在设置业务流程并映射消息、 端口和架构后必须生成 BizTalk 解决方案。 为生成项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，你将需要一个程序集密钥文件。 成功生成解决方案后，你必须部署解决方案。  
  
    > [!NOTE]
    >  根据后面的主题的更多详细说明这些高级任务，包括的过程信息而提供。  
  
 一旦部署了解决方案，你的设计时间任务完成。 你现在必须执行的运行的时任务。  
  
## <a name="run-time-tasks"></a>运行时任务  
  
-   **配置应用程序**。 在设计时部署的 BizTalk 项目将显示在 BizTalk Server 管理控制台为业务流程。 必须映射到现在必须创建使用 BizTalk Server 管理控制台的物理端口的设计时创建的逻辑端口来配置此业务流程。  
  
     上的物理端口，必须指定"操作"或"操作映射"。 此操作对应于你想要在 Siebel 系统上执行该操作。 你需要设置操作，如果你不使用动态操作。 
  
-   **启动应用程序**。 配置应用程序后，您必须启动该应用程序，并将输入的消息放在定义的文件位置。 业务流程使用输入的消息和将其传递给 Siebel 系统并接收响应。 此响应将可供你在另一个定义的文件位置。  
  
 若要完成这些高级的设计时和运行时任务，你还必须执行其他任务。 例如，当使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]要生成的架构，你必须指定连接 URI 以连接到 Siebel 系统。 本部分提供信息在这种重复任务上，你必须执行通过开发 BizTalk 应用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
