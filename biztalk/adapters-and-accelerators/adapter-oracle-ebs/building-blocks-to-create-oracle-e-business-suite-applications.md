---
title: 若要创建 Oracle E-business Suite 的应用程序的构建基块 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 483a52d4-1aaf-46b1-bb42-9f91bf678346
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b615f5a1e021a0db1d9dcc4b5780a8e6c55a547c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013142"
---
# <a name="building-blocks-to-create-oracle-e-business-suite-applications"></a>若要创建 Oracle E-business Suite 的应用程序的构建基块
若要通过执行对 Oracle E-business Suite 操作[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，必须执行的一组使用的设计时和运行时任务[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中分别。 本部分概述了这些任务。 本部分中，其中演示如何执行对 Oracle E-business Suite 使用的特定操作的所有主题[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，依据这些高级任务。  
  
## <a name="using-visual-studio"></a>使用 Visual Studio  
  
1. **创建 BizTalk 项目，并生成架构**。 必须创建的 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，并为你将 Oracle E-business Suite 执行的操作生成架构。 例如，如果你想要从 Oracle E-business Suite 界面表中选择记录，必须生成为该表选择操作的架构。 若要生成架构，必须使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 有关详细信息，请参阅[检索用于 Oracle E-business Suite 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-oracle-ebs/get-metadata-for-oracle-e-business-suite-operations-in-visual-studio.md)。  
  
2. **设置业务流程**。 一旦您已经生成架构，必须通过使用业务流程设计器来设置业务流程。 对于基本的业务流程，您将添加发送和接收形状以及发送和接收逻辑端口。 在后续步骤中，则这些逻辑端口映射到物理端口使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。 业务流程使用这些端口选取适配器客户端发送的消息。 然后，业务流程将消息传递到 Oracle E-business Suite。 Oracle E-business Suite 发送的响应，一旦业务流程将传递回适配器客户端的响应。  
  
3. **创建消息，并链接到架构**。 在您的业务流程，必须创建将映射到第一步中生成的架构的消息。 通常情况下，创建请求消息和响应消息。 这些消息映射到相应的请求和响应架构。  
  
4. **将消息形状映射到的消息和端口**。 在您的业务流程，现在必须映射到第三个步骤中创建的消息在第二个步骤中添加每个形状。 此外必须将消息形状映射到用于发送该消息的端口。  
  
    例如，如果您的业务流程中的第一个形状，将收到一条消息的接收形状您将此形状映射到请求消息并将请求消息发送端口。  
  
5. **生成并部署 BizTalk 项目**。 安装了业务流程和映射的消息、 端口和架构后，必须生成 BizTalk 解决方案。 生成项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，所需程序集密钥文件。 已成功生成解决方案后，必须部署解决方案。  
  
> [!NOTE]
>  在本部分的各主题中提供的这些高级任务，包括步骤的信息，更多详细的说明。  
  
 一旦您已成功地构建和部署 BizTalk 项目，在设计时中的任务[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]来完成。 现在必须执行某些运行时任务使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
## <a name="using-the-biztalk-server-administration-console"></a>使用 BizTalk Server 管理控制台  
  
1. **配置应用程序**。 通过使用部署的 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]会显示在[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]作为业务流程管理控制台。 必须通过将映射中创建的逻辑端口来配置此业务流程[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]与你现在必须创建使用的物理端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
    上的物理端口，必须指定"操作"或"操作映射"。 此操作对应于你想要对 Oracle E-business Suite 执行该操作。 您需要指定的操作，如果不使用动态操作。 有关操作的详细信息，请参阅[适用于 Oracle E-business Suite 中配置 SOAP 操作](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md)。  
  
2. **启动应用程序**。 配置应用程序后，您必须启动该应用程序，并将请求消息放在定义的文件位置。 业务流程使用的请求消息、 将其传递给 Oracle E-business Suite，并接收响应。 此响应可供适配器客户端，另一个定义的文件位置。  
  
   若要完成这些高级任务，您必须执行其他任务。 例如，使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]若要生成的架构，必须指定连接到 Oracle E-business Suite 连接 URI。 本部分提供的信息在此类重复性任务上，你必须执行在开发 BizTalk 应用程序使用[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [将 Oracle E-business Suite 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)  
  
-   [配置适用于 Oracle E-business Suite 连接 URI](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-connection-uri-for-oracle-e-business-suite.md)  
  
-   [用于 Oracle E-business Suite 中配置单一登录凭据](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-sign-in-credentials-for-the-oracle-e-business-suite.md)  
  
-   [用于 Oracle E-business Suite 中配置的绑定属性](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-binding-properties-for-oracle-e-business-suite.md)  
  
-   [配置用于 Oracle E-business Suite 的 SOAP 操作](../../adapters-and-accelerators/adapter-oracle-ebs/configure-the-soap-action-for-oracle-e-business-suite.md)  
  
-   [手动配置物理端口绑定到 Oracle E-business 适配器](../../adapters-and-accelerators/adapter-oracle-ebs/manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter.md)  
  
-   [配置使用到 Oracle E-business Suite 的端口绑定文件的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)  
  
-   [使用 Oracle E-business Suite 中配置动态端口](../../adapters-and-accelerators/adapter-oracle-ebs/configure-dynamic-ports-with-oracle-e-business-suite.md)  
  
-   [使用 Oracle E-business Suite 的重用适配器绑定](../../adapters-and-accelerators/adapter-oracle-ebs/reuse-adapter-bindings-with-oracle-e-business-suite.md)  
  
## <a name="see-also"></a>请参阅  
 [开发 BizTalk 应用程序](../../core/developing-biztalk-server-applications.md)