---
title: "创建 Oracle E-business Suite 应用程序的构建基块 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 483a52d4-1aaf-46b1-bb42-9f91bf678346
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0450f672573153df803f875a0dbac1436f8f4760
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="building-blocks-to-create-oracle-e-business-suite-applications"></a>创建 Oracle E-business Suite 应用程序的构建基块
若要通过执行对 Oracle E-business Suite 操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，必须执行一组使用的设计时和运行时任务[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]分别管理控制台。 本部分概述了这些任务。 本部分中，用于演示如何执行对 Oracle E-business Suite 使用的特定操作的所有主题[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，这些高级任务进行建模。  
  
## <a name="using-visual-studio"></a>使用 Visual Studio  
  
1.  **创建 BizTalk 项目，然后生成架构**。 你必须创建中的 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，并生成将在 Oracle E-business Suite 上执行操作的架构。 例如，如果你想要从 Oracle E-business Suite 接口表中选择记录，你必须生成为该表选择操作的架构。 若要生成架构，必须使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 有关详细信息，请参阅[检索用于 Oracle E-business Suite 操作 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)。  
  
2.  **设置业务流程**。 一旦你已生成架构，必须通过使用 Orchestration 设计器来设置业务流程。 适用于基本的业务流程，你将添加发送和接收形状以及发送和接收逻辑端口。 在后续步骤中你这些逻辑将端口映射到物理端口使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 业务流程使用这些端口选取适配器客户端发送的消息。 然后，业务流程将消息传递到 Oracle E-business Suite。 一旦 Oracle E-business Suite 发送响应时，业务流程将传递回适配器客户端的响应。  
  
3.  **创建消息，并将链接到架构**。 在您的业务流程，你必须创建将映射到第一步中生成的架构的消息。 通常情况下，你创建的请求消息和响应消息。 这些消息映射到相应的请求和响应架构。  
  
4.  **将消息形状映射到消息和端口**。 在您的业务流程，现在必须映射到第三个步骤中创建的消息的第二步中添加每个形状。 你还必须将消息形状映射到该消息将发送在其的端口。  
  
     例如，如果您的业务流程中的第一个形状，将收到一条消息的接收形状你将此形状映射到请求消息和发送请求消息的端口。  
  
5.  **生成并部署 BizTalk 项目**。 已设置了业务流程和映射的消息、 端口和架构后，你必须生成 BizTalk 解决方案。 为生成项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，你需要一个程序集密钥文件。 成功生成解决方案后，你必须部署解决方案。  
  
> [!NOTE]
>  中的这一部分的各个主题提供了包括的过程信息，这些高级任务的更多详细的说明。  
  
 一旦成功，你已生成并部署 BizTalk 项目，你的设计时中的任务[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]完成。 现在，你必须执行使用某些运行时任务[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
## <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1.  **配置应用程序**。 通过使用部署的 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]显示在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]按业务流程的管理控制台。 你必须通过映射中创建的逻辑端口来配置此业务流程[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]到现在必须创建使用的物理端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
     上的物理端口，必须指定"操作"或"操作映射"。 此操作对应于你想要对 Oracle E-business Suite 执行该操作。 你需要指定的操作，如果你不使用动态操作。 有关操作的详细信息，请参阅[为 Oracle E-business Suite 配置 SOAP 操作](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md)。  
  
2.  **启动应用程序**。 配置应用程序后，您必须启动该应用程序，并将请求消息放在定义的文件位置。 业务流程使用请求消息、 将其传递给 Oracle E-business Suite，并接收响应。 此响应是可用于在另一个定义的文件位置适配器客户端。  
  
 若要完成这些高级任务，你还必须执行其他任务。 例如，当使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]要生成的架构，你必须指定连接 URI 以连接到 Oracle E-business Suite。 本部分提供信息在这种重复任务上，你必须执行开发 BizTalk 应用程序使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [将 Oracle E-business Suite 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)  
  
-   [配置 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)  
  
-   [为 Oracle E-business Suite 配置登录凭据](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-sign-in-credentials-for-the-oracle-e-business-suite.md)  
  
-   [为 Oracle E-business Suite 配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)  
  
-   [配置用于 Oracle E-business Suite 的 SOAP 操作](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md)  
  
-   [手动配置物理端口绑定到 Oracle E-business 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)  
  
-   [配置使用的端口绑定文件，以便 Oracle E-business Suite 的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)  
  
-   [使用 Oracle E-business Suite 配置动态端口](../../adapters-and-accelerators/adapter-oracle-ebs/configure-dynamic-ports-with-oracle-e-business-suite.md)  
  
-   [重复使用 Oracle E-business Suite 适配器绑定](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)  
  
## <a name="see-also"></a>另请参阅  
 [开发 BizTalk 应用程序](../../core/developing-biztalk-server-applications.md)