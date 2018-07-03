---
title: 若要创建的 SAP 应用程序的构建基块 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- design-time tasks
- run-time tasks
- developing, fundamentals of (BizTalk applications)
ms.assetid: 591a5597-5e7d-44b0-8bee-e1c987c5e6c3
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e0ff492d48538a54313d85202618e099e984fc3e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37006022"
---
# <a name="building-blocks-to-create-sap-applications"></a>若要创建的 SAP 应用程序的构建基块
对 SAP 系统使用执行操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]涉及两个组的活动： 设计时活动和运行时活动。 若要使用执行 SAP 系统的操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，必须执行的一组使用的设计时和运行时任务[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中分别。 本部分概述了这些任务。 本部分中，其中演示如何执行对 SAP 系统使用的特定操作的所有主题[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，依据这些高级任务。  
  
## <a name="design-time-tasks"></a>设计时任务  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供了功能浏览、 搜索和检索 Rfc、 Bapi 和使用 XML 架构定义语言 (Xsd) 形式的 Idoc 的 SAP 元数据[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 Xsd 是特定于你想要在 SAP 系统上，执行该操作并[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]可仅创建 BizTalk 项目。 在设计时需要执行以下任务。  
  
- **创建 BizTalk 项目，并生成架构**。 开始时，必须在 Microsoft 中创建 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和的 RFC 将 SAP 系统中调用生成的架构。 例如，如果你想要调用 RFC_CUSTOMER_GET SAP 系统中，您必须为 RFC_CUSTOMER_GET 生成元数据。 在此步骤中使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成的架构。 有关详细信息，请参阅[获取 SAP 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-sap/get-metadata-for-sap-operations-in-visual-studio.md)。  
  
- **设置业务流程**。 一旦您已经生成架构，必须通过使用业务流程设计器来设置业务流程。 对于基本的业务流程，您将添加发送和接收形状以及发送和接收逻辑端口。 在后续步骤中，则这些逻辑端口映射到物理端口使用 BizTalk Server 管理控制台。 业务流程使用这些端口选取适配器客户端发送的消息。 然后，业务流程将消息传递到 SAP 系统。 一旦从 SAP 系统收到响应，业务流程将传递到适配器客户端的响应。  
  
- **创建消息并将链接到架构**。 在您的业务流程，必须创建将映射到第一步中生成的架构的消息。 通常情况下，创建请求消息和响应消息。 这些消息映射到相应的请求和响应架构。  
  
- **将消息形状映射到的消息和端口**。 在您的业务流程，现在必须映射到第三个步骤中创建的消息在第二个步骤中添加的每个形状。 此外必须将消息形状映射到用于发送该消息的端口。  
  
   例如，如果第一个形状在业务流程中的接收消息的接收形状，您将此形状映射到请求消息并将请求消息发送端口。  
  
- **生成并部署 BizTalk 项目**。 在设置业务流程并映射消息、 端口和架构后必须生成 BizTalk 解决方案。 生成项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，需要将程序集密钥文件。 已成功生成解决方案后，必须部署解决方案。  
  
  > [!NOTE]
  >  在本部分的各主题中提供的这些高级任务，包括步骤的信息，更多详细的说明。  
  
  一旦部署该解决方案，通过实现设计时任务。 现在必须执行的运行时任务。  
  
## <a name="run-time-tasks"></a>运行任务  
 在运行时，可以使用 BizTalk Server 管理控制台来部署和监视在设计时创建的业务流程。 此外，您必须：  
  
- **配置应用程序**。 在设计时部署的 BizTalk 项目显示在 BizTalk Server 管理控制台为业务流程。 必须通过将映射到现在必须创建使用的物理端口的设计时创建的逻辑端口来配置此业务流程[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
   上的物理端口，必须指定"操作"或"操作映射"。 此操作对应于你想要在 SAP 系统上执行该操作。 您需要设置的操作，如果不使用动态操作。 
  
- **启动应用程序**。 配置应用程序后，您必须启动该应用程序，并将输入的消息放在定义的文件位置。 业务流程使用的输入的消息并将其传递到 SAP 系统并接收响应。 此响应将可供你在另一个定义的文件位置。  
  
  若要完成这些高级设计时和运行任务，您必须执行其他任务。 例如，使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]若要生成的架构，必须指定连接 URI 连接到 SAP 系统。 本部分提供的信息在此类重复性任务上，你必须执行在开发 BizTalk 应用程序使用[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [将 SAP 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)  
  
-   [配置 SAP 适配器的连接 URI](../../adapters-and-accelerators/adapter-sap/configure-the-connection-uri-for-the-sap-adapter.md)  
  
-   [配置 SAP 系统的凭据登录](../../adapters-and-accelerators/adapter-sap/configure-the-sign-in-credentials-for-the-sap-system.md) 
  
-   [配置 SAP 适配器的绑定属性](../../adapters-and-accelerators/adapter-sap/configure-the-binding-properties-for-the-sap-adapter.md)
  
-   [配置用于 SAP 系统的 SOAP 操作](../../adapters-and-accelerators/adapter-sap/configure-the-soap-action-for-the-sap-system.md)
  
-   [手动配置到 SAP 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sap/manually-configure-a-physical-port-binding-to-the-sap-adapter.md)
  
-   [配置使用到 SAP 的端口绑定文件的物理端口绑定](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)
  
-   [SAP 适配器配置动态端口](../../adapters-and-accelerators/adapter-sap/configure-dynamic-ports-in-the-sap-adapter.md)
  
-   [重复使用 SAP 适配器绑定](../../adapters-and-accelerators/adapter-sap/reuse-sap-adapter-bindings.md)
  
## <a name="see-also"></a>请参阅  
[使用 SAP 适配器开发 BizTalk 应用程序](../../adapters-and-accelerators/adapter-sap/develop-biztalk-applications-using-the-sap-adapter.md)