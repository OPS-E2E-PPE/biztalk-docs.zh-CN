---
title: "开发与 Oracle 数据库的 BizTalk 应用程序的构建基块 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- developing, BizTalk applications
- run-time tasks
- design-time tasks
ms.assetid: ad9ca856-5569-41ab-8617-ae6db5e3b4d7
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0747569ef58e1f2223baefba6c51b77b205eb0d3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="building-blocks-to-develop-biztalk-applications-with-oracle-database"></a>开发与 Oracle 数据库的 BizTalk 应用程序的构建基块
通过执行对 Oracle 数据库的操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]涉及两个任务组： 设计时和运行时。  
  
## <a name="design-time-tasks"></a>设计时任务  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供能够浏览、 搜索和检索表、 存储的过程和其他此类项的 XML 架构定义语言 (Xsd) 形式的 Oracle 元数据使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。 Xsd 是特定于你想要对 Oracle 数据库执行该操作。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]是仅当你创建 BizTalk 项目时，才可用。 在设计时需要执行以下任务：  
  
-   **创建 BizTalk 项目，并生成架构**。 必须在 Microsoft 中创建 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]并生成将 Oracle 数据库执行的操作的架构。 例如，如果你想要将一个记录插入员工表，你必须生成员工表的插入操作的元数据。 在此步骤中，你使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成架构。 有关详细信息，请参阅[为 Visual Studio 中的 Oracle 数据库操作获取元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)。
  
-   **设置业务流程**。 一旦你已生成架构，必须通过使用 Orchestration 设计器来设置业务流程。 适用于基本的业务流程，你将添加发送和接收形状以及发送和接收逻辑端口。 在后续步骤中你这些逻辑将端口映射到物理端口使用 BizTalk Server 管理控制台。 业务流程使用这些端口选取适配器客户端发送的消息。 然后，业务流程将消息传递到 Oracle 数据库。 一旦从 Oracle 数据库收到的响应，业务流程将传递对适配器客户端的响应。  
  
-   **创建消息并将链接到架构**。 在您的业务流程，你必须创建将映射到第一步中生成的架构的消息。 通常情况下，你创建的请求消息和响应消息。 这些消息映射到相应的请求和响应架构。  
  
-   **将消息形状映射到消息和端口**。 在您的业务流程，现在必须映射到第三个步骤中创建的消息的第二步中添加每个形状。 你还必须将消息形状映射到该消息将发送在其的端口。  
  
     例如，如果您的业务流程中的第一个形状，将收到一条消息的接收形状你将此形状映射到请求消息和发送请求消息的端口。  
  
-   **生成并部署 BizTalk 项目**。 已设置了业务流程和映射的消息、 端口和架构后，你必须生成 BizTalk 解决方案。 为生成项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，你需要一个程序集密钥文件。 成功生成解决方案后，你必须部署解决方案。  
  
    > [!NOTE]
    >  中的这一部分的各个主题提供了包括的过程信息，这些高级任务的更多详细的说明。  
  
 一旦部署了解决方案，你的设计时任务完成。 你现在必须执行的运行时任务。  
  
## <a name="run-time-tasks"></a>运行时任务  
 在运行时，可以使用 BizTalk Server 管理控制台来部署和监视在设计时创建业务流程。 此外，你必须：  
  
-   **配置应用程序**。 在设计时部署的 BizTalk 项目显示在 BizTalk Server 管理控制台中按业务流程。 必须映射到现在必须创建使用 BizTalk Server 管理控制台的物理端口的设计时创建的逻辑端口来配置此业务流程。  
  
     上的物理端口，必须指定"操作"或"操作映射"。 此操作对应于你想要对 Oracle 数据库执行该操作。 你需要设置操作，如果你不使用动态操作。  
  
-   **启动应用程序**。 配置应用程序后，您必须启动该应用程序，并将输入的消息放在定义的文件位置。 业务流程使用输入的消息和将其传递到 Oracle 数据库并接收响应。 此响应将可供你在另一个定义的文件位置。  
  
 若要完成这些高级的设计时和运行时任务，你还必须执行其他任务。 例如，当使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]要生成的架构，你必须指定要连接到 Oracle 数据库 URI 的连接。 本部分提供信息在这种重复任务上，你必须执行开发 BizTalk 应用程序使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  

  
## <a name="see-also"></a>另请参阅  
[开发使用 Oracle 数据库适配器的 BizTalk 应用程序](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)