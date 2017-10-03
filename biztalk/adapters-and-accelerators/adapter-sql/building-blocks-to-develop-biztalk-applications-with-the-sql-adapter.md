---
title: "开发具有 SQL 适配器的 BizTalk 应用程序的构建基块 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fac7cbf4-b111-43ad-8726-36d037918c9c
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58198376a5ce42fc9c77fc18822c2ed739e5db00
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="building-blocks-to-develop-biztalk-applications-with-the-sql-adapter"></a>开发具有 SQL 适配器的 BizTalk 应用程序的构建基块
若要通过使用执行 SQL Server 上的操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，必须执行一组使用的设计时和运行时任务[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]分别管理控制台。 本部分概述了这些任务。 本部分中，用于演示如何执行 SQL Server 使用的特定操作的所有主题[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，这些高级任务进行建模。  
  
## <a name="using-visual-studio"></a>使用 Visual Studio  
  
1.  **创建 BizTalk 项目，然后生成架构**。 你必须创建中的 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，并生成将在 SQL Server 上执行操作的架构。 例如，如果你想要在 SQL Server 表中插入记录，你必须生成该表的 Insert 操作架构。 若要生成架构，必须使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 有关详细信息，请参阅[检索元数据使用的 SQL 适配器的 Visual Studio 中的 SQL Server 操作](../../adapters-and-accelerators/adapter-sql/get-metadata-for-sql-server-operations-in-visual-studio-using-the-sql-adapter.md)。  
  
2.  **设置业务流程**。 一旦你已生成架构，必须通过使用 Orchestration 设计器来设置业务流程。 适用于基本的业务流程，你将添加发送和接收形状以及发送和接收逻辑端口。 在后续步骤中你这些逻辑将端口映射到物理端口使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 业务流程使用这些端口选取适配器客户端发送的消息。 然后，业务流程将消息传递到 SQL Server。 后 SQL Server 发送响应时，业务流程将传递回适配器客户端的响应。  
  
3.  **创建消息，并将链接到架构**。 在您的业务流程，你必须创建将映射到第一步中生成的架构的消息。 通常情况下，你创建的请求消息和响应消息。 这些消息映射到相应的请求和响应架构。  
  
4.  **将消息形状映射到消息和端口**。 在您的业务流程，现在必须映射到第三个步骤中创建的消息的第二步中添加每个形状。 你还必须将消息形状映射到该消息将发送在其的端口。  
  
     例如，如果您的业务流程中的第一个形状，将收到一条消息的接收形状你将此形状映射到请求消息和发送请求消息的端口。  
  
5.  **生成并部署 BizTalk 项目**。 已设置了业务流程和映射的消息、 端口和架构后，你必须生成 BizTalk 解决方案。 为生成项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，你需要一个程序集密钥文件。 成功生成解决方案后，你必须部署解决方案。  
  
> [!NOTE]
>  中的这一部分的各个主题提供了包括的过程信息，这些高级任务的更多详细的说明。  
  
 一旦你已成功生成并部署 BizTalk 项目，你的任务中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]完成。 现在，你必须执行使用某些任务[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
## <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1.  **配置应用程序**。 通过使用部署的 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]显示在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]按业务流程的管理控制台。 你必须通过映射中创建的逻辑端口来配置此业务流程[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]到现在必须创建使用的物理端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
     上的物理端口，必须指定"操作"或"操作映射"。 此操作对应于你想要在 SQL Server 上执行该操作。 你需要指定的操作，如果你不使用动态操作。 有关操作的详细信息，请参阅[配置 SQL 适配器的 SOAP 操作](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md)。  
  
2.  **启动应用程序**。 配置应用程序后，您必须启动该应用程序，并将请求消息放在定义的文件位置。 业务流程使用请求消息、 将其传递给 SQL Server，并接收响应。 此响应是可用于在另一个定义的文件位置适配器客户端。  
  
 若要完成这些高级任务，你还必须执行其他任务。 例如，当使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]要生成的架构，你必须指定连接 URI 来连接到 SQL Server。 本部分提供信息在这种重复任务上，你必须执行开发 BizTalk 应用程序使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [将 SQL 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)  
  
-   [配置 SQL 适配器的连接 URI](../../adapters-and-accelerators/adapter-sql/configure-the-connection-uri-for-the-sql-adapter.md)  
  
-   [配置 SQL 适配器的凭据登录](../../adapters-and-accelerators/adapter-sql/configure-the-sign-in-credentials-for-the-sql-adapter.md)
  
-   [配置 SQL 适配器的绑定属性](../../adapters-and-accelerators/adapter-sql/configure-the-binding-properties-for-the-sql-adapter.md) 
  
-   [配置 SQL 适配器的 SOAP 操作](../../adapters-and-accelerators/adapter-sql/configure-the-soap-action-for-the-sql-adapter.md)
  
-   [手动配置到 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/manually-configure-a-physical-port-binding-to-the-sql-adapter.md) 
  
-   [配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)
  
-   [配置动态端口](../../adapters-and-accelerators/adapter-sql/configure-dynamic-ports-in-the-sql-adapter.md)
  
-   [重用适配器绑定](../../adapters-and-accelerators/adapter-sql/reuse-sql-adapter-bindings.md)
  
## <a name="see-also"></a>另请参阅  
[开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sql/develop-biztalk-applications-using-the-sql-adapter.md)