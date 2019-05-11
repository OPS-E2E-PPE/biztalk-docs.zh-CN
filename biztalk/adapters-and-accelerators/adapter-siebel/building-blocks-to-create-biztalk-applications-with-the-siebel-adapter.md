---
title: 若要创建与 Siebel 适配器的 BizTalk 应用程序的构建基块 |Microsoft Docs
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
ms.openlocfilehash: 3006aef526f00a0bed59bca69e39c9a748a05037
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371955"
---
# <a name="building-blocks-to-create-biztalk-applications-with-the-siebel-adapter"></a>若要创建与 Siebel 适配器的 BizTalk 应用程序的构建基块
执行操作上 Siebel 系统使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]涉及两个组的活动： 设计时活动和运行时活动。 若要使用执行 Siebel 系统的操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，必须执行的一组使用的设计时和运行时任务[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中分别。 本部分概述了这些任务。 本部分中，其中演示如何执行特定操作 Siebel 系统使用的所有主题[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，依据这些高级任务。  
  
## <a name="design-time-tasks"></a>设计时任务  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供了功能浏览、 搜索和检索业务组件和业务服务的使用 XML 架构定义语言 (Xsd) 形式的 Siebel 元数据[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 Xsd 是特定于你想要在 Siebel 系统中执行该操作并[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]可仅创建 BizTalk 项目。 在设计时可能需要执行以下任务。  
  
- **创建 BizTalk 项目，并生成架构**。 开始时，必须在 Microsoft 中创建 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]并生成业务组件或将 Siebel 系统中调用的业务服务的架构。 例如，如果你想要帐户业务组件中插入一条记录，必须生成帐户业务组件的插入操作的元数据。 在此步骤中使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]生成的架构。 有关详细信息，请参阅[获取 Siebel 操作在 Visual Studio 中的元数据](../../adapters-and-accelerators/adapter-siebel/get-metadata-for-siebel-operations-in-visual-studio.md)。  
  
- **设置业务流程**。 一旦您已经生成架构，必须通过使用业务流程设计器来设置业务流程。 对于基本的业务流程，您将添加发送和接收形状以及发送和接收逻辑端口。 在后续步骤中，您将这些逻辑端口映射到物理端口，通过使用 BizTalk Server 管理控制台。 业务流程使用这些端口选取由适配器客户端发送的消息。 然后，业务流程将消息传递到 Siebel 系统。 一旦从 Siebel 系统收到响应，该业务流程将传递到适配器客户端的响应。  
  
- **创建消息并将链接到架构**。 在您的业务流程，必须创建将映射到第一步中生成的架构的消息。 通常情况下，您需要创建请求和响应消息。 这些消息映射到相应的请求和响应架构。  
  
- **将消息形状映射到的消息和端口**。 在您的业务流程，现在必须映射到第三个步骤中创建的消息在第二个步骤中添加的每个形状。 此外必须将消息形状映射到用于发送该消息的端口。  
  
   例如，如果您的业务流程中的第一个形状，将收到一条消息的接收形状会将此形状映射为"请求"消息并将请求消息发送端口。  
  
- **生成并部署 BizTalk 项目**。 在设置业务流程并映射消息、 端口和架构后必须生成 BizTalk 解决方案。 生成项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，需要将程序集密钥文件。 已成功生成解决方案后，必须部署解决方案。  
  
  > [!NOTE]
  >  更多详细说明这些高级别任务，包括的过程信息的主题，请按照下提供。  
  
  一旦部署该解决方案，通过实现在设计时任务。 现在必须执行的运行的时任务。  
  
## <a name="run-time-tasks"></a>运行任务  
  
- **配置应用程序**。 在设计时部署的 BizTalk 项目将显示在 BizTalk Server 管理控制台为业务流程。 通过将映射到现在必须创建使用 BizTalk Server 管理控制台的物理端口的设计时创建的逻辑端口，必须配置此业务流程。  
  
   上的物理端口，必须指定"操作"或"操作映射"。 此操作对应于你想要在 Siebel 系统中执行该操作。 您需要设置的操作，如果不使用动态操作。 
  
- **启动应用程序**。 配置应用程序后，您必须启动该应用程序，并将输入的消息放在定义的文件位置。 业务流程使用的输入的消息并将其传递到 Siebel 系统并接收响应。 此响应将可供你在另一个定义的文件位置。  
  
  若要完成这些高级设计时和运行任务，您必须执行其他任务。 例如，使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]或[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]若要生成的架构，必须指定连接到 Siebel 系统连接 URI。 本部分提供的信息在此类重复性任务上，你必须执行在开发 BizTalk 应用程序使用[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。  
  
