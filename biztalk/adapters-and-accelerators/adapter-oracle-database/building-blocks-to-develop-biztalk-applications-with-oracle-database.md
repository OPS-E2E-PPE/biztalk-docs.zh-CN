---
title: 若要开发与 Oracle 数据库的 BizTalk 应用程序的构建基块 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- developing, BizTalk applications
- run-time tasks
- design-time tasks
ms.assetid: ad9ca856-5569-41ab-8617-ae6db5e3b4d7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 703bff35321fcedb4240d8ced1f422707c0ca51e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973798"
---
# <a name="building-blocks-to-develop-biztalk-applications-with-oracle-database"></a>若要开发与 Oracle 数据库的 BizTalk 应用程序的构建基块
通过执行对 Oracle 数据库的操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]涉及两个任务组： 设计时和运行时。  
  
## <a name="design-time-tasks"></a>设计时任务  
 [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]提供了功能浏览、 搜索和检索表、 存储的过程和其他此类项目中的 XML 架构定义语言 (Xsd) 形式的 Oracle 元数据使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]。 Xsd 是特定于你想要对 Oracle 数据库执行该操作。 [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]可仅创建 BizTalk 项目。 在设计时需要执行以下任务：  
  
- **创建 BizTalk 项目，并生成架构**。 必须在 Microsoft 中创建 BizTalk 项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]和生成将 Oracle 数据库执行该操作的架构。 例如，如果你想要的 EMPLOYEE 表中插入一条记录，必须生成为 EMPLOYEE 表的 Insert 操作的元数据。 在此步骤中，您使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]生成的架构。 有关详细信息，请参阅[获取 Visual Studio 中的 Oracle 数据库操作的元数据](../../adapters-and-accelerators/adapter-oracle-database/get-metadata-for-oracle-database-operations-in-visual-studio.md)。
  
- **设置业务流程**。 一旦您已经生成架构，必须通过使用业务流程设计器来设置业务流程。 对于基本的业务流程，您将添加发送和接收形状以及发送和接收逻辑端口。 在后续步骤中，则这些逻辑端口映射到物理端口使用 BizTalk Server 管理控制台。 业务流程使用这些端口选取适配器客户端发送的消息。 然后，业务流程将消息传递到 Oracle 数据库。 一旦从 Oracle 数据库收到响应，业务流程将传递到适配器客户端的响应。  
  
- **创建消息并将链接到架构**。 在您的业务流程，必须创建将映射到第一步中生成的架构的消息。 通常情况下，创建请求消息和响应消息。 这些消息映射到相应的请求和响应架构。  
  
- **将消息形状映射到的消息和端口**。 在您的业务流程，现在必须映射到第三个步骤中创建的消息在第二个步骤中添加每个形状。 此外必须将消息形状映射到用于发送该消息的端口。  
  
   例如，如果您的业务流程中的第一个形状，将收到一条消息的接收形状您将此形状映射到请求消息并将请求消息发送端口。  
  
- **生成并部署 BizTalk 项目**。 安装了业务流程和映射的消息、 端口和架构后，必须生成 BizTalk 解决方案。 生成项目[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，所需程序集密钥文件。 已成功生成解决方案后，必须部署解决方案。  
  
  > [!NOTE]
  >  在本部分的各主题中提供的这些高级任务，包括步骤的信息，更多详细的说明。  
  
  一旦部署该解决方案，通过实现设计时任务。 现在必须执行的运行时任务。  
  
## <a name="run-time-tasks"></a>运行任务  
 在运行时，可以使用 BizTalk Server 管理控制台来部署和监视在设计时创建的业务流程。 此外，您必须：  
  
- **配置应用程序**。 在设计时部署的 BizTalk 项目显示在 BizTalk Server 管理控制台为业务流程。 通过将映射到现在必须创建使用 BizTalk Server 管理控制台的物理端口的设计时创建的逻辑端口，必须配置此业务流程。  
  
   上的物理端口，必须指定"操作"或"操作映射"。 此操作对应于你想要对 Oracle 数据库执行该操作。 您需要设置的操作，如果不使用动态操作。  
  
- **启动应用程序**。 配置应用程序后，您必须启动该应用程序，并将输入的消息放在定义的文件位置。 业务流程使用的输入的消息并将其传递到 Oracle 数据库并接收响应。 此响应将可供你在另一个定义的文件位置。  
  
  若要完成这些高级设计时和运行任务，您必须执行其他任务。 例如，当使用[!INCLUDE[consumeadapterservlong](../../includes/consumeadapterservlong-md.md)]若要生成的架构，必须指定连接 URI 连接到 Oracle 数据库。 本部分提供的信息在此类重复性任务上，你必须执行在开发 BizTalk 应用程序使用[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。  
  

  
## <a name="see-also"></a>请参阅  
[开发 BizTalk 应用程序使用 Oracle 数据库适配器](../../adapters-and-accelerators/adapter-oracle-database/develop-biztalk-applications-using-the-oracle-database-adapter.md)