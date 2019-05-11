---
title: 第 1 步：为操作生成架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63218a5e-9af2-40af-9992-ac5e204d2832
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bfc8f1aaf02b2dc28c4612ee5ce3df879d8ed938
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367868"
---
# <a name="step-1-generate-schema-for-operations"></a>第 1 步：为操作生成架构
![2 的第 1 步](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")  
  
 **若要完成的时间：** 5 分钟  
  
 **目标：** 在此步骤中，生成使用 SQL Server 数据库执行操作的架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。 对于本教程中，必须生成以下架构：  
  
-   **通知**（入站操作）。  
  
-   **UPDATE_EMPLOYEE**存储过程 （出站操作）。  
  
-   **插入**上的操作**Purchase_Order**表 （出站操作）。  
  
## <a name="prerequisites"></a>先决条件  
 您继续阅读本教程之前，请确保：  
  
-   你必须完成中的步骤[之前在开发 BizTalk 应用程序](http://msdn.microsoft.com/library/3539741d-5266-43d4-9b7b-73e82f0ed4f6)。  
  
-   必须以 BizTalk Server Administrators 组的成员身份登录。  
  
### <a name="to-generate-schema-for-operations"></a>若要为操作生成架构  
  
1. 创建新的 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。 对于本教程，将项目命名为`Employee_PurchaseOrder`。  
  
2. ADAPTER_SAMPLES SQL Server 数据库使用连接到[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。 有关如何使用连接的说明[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，请参阅[连接到 Visual Studio 使用使用适配器服务外接程序中的 SQL Server](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)。  
  
   > [!NOTE]
   >  此外可以连接到 SQL Server 使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。 但是，对于本教程将使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
3. 生成架构**通知**的入站操作。  
  
   1. 连接到 ADAPTER_SAMPLES 数据库中，在以后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，从**选择协定类型**列表中，选择**服务 （入站操作）**。  
  
   2. 从**选择一个类别**框中，单击根节点 (**/**)。  
  
   3. 从**可用类别和操作**框中，选择**通知**然后单击**添加**。 **通知**操作现在显示在**添加的类别和操作**框。 单击“确定” 。  
  
4. 生成架构**UPDATE_EMPLOYEE**存储过程和插入操作上**Purchase_Order**表。  
  
   1. 重复步骤 2 以连接到 SQL Server 使用 ADAPTER_SAMPLES 数据库[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。  
  
      > [!NOTE]
      >  不能在同一时间生成的入站和出站操作的架构。 因此，第 3 步中，单击后**确定**若要生成的架构**通知**操作，[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]关闭。 您必须重新连接到 SQL Server 数据库来为出站操作生成架构。  
  
   2. 从**选择协定类型**列表中，选择**客户端 （出站操作）**。  
  
   3. 从**选择一个类别**框中，单击**Strongly-Typed 过程**节点。 从**可用类别和操作**s 框中，选择**UPDATE_EMPLOYEE**，然后单击**添加**。  
  
      > [!IMPORTANT]
      >  **UPDATE_EMPLOYEE**存储的过程中也有下**过程**节点。 但是，如果生成从下的存储过程的架构**过程**节点，响应消息架构在设计时不可用，但收到了响应消息后执行存储的过程。  
      >   
      >  在本教程中，您将映射到插入操作的输入架构的存储过程的响应架构上**Purchase_Order**表。 因此，您将需要的架构**UPDATE_EMPLOYEE**在设计时和你的存储的过程必须选择从下的存储的过程**Strongly-Typed 过程**。 通过此操作，将在设计时获取的存储过程的架构。  
  
   4. 从**选择一个类别**框中，展开**表**节点，然后单击的节点**Purchase_Order**表。 从**可用类别和操作**s 框中，选择**插入**，单击**添加**，然后单击**确定**。  
  
## <a name="what-did-i-just-do"></a>我只需做了什么？  
 在此步骤中，生成的架构**通知**（入站操作）， **UPDATE_EMPLOYEE**存储过程，并**插入**操作**Purchase_Order**表。 生成架构后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]向 BizTalk 项目中添加以下文件：  
  
- 包含要调用 SQL Server 上的操作的请求消息的架构的 XSD 文件。  
  
- 可用于创建 WCF 自定义发送和接收端口中的 XML 绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
  有关生成架构的详细信息，请参阅[浏览、 搜索和获取元数据的 SQL 操作使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter.md)。  
  
## <a name="next-steps"></a>后续步骤  
 中的架构在 BizTalk 项目中创建消息[步骤 2:为 BizTalk 业务流程创建消息](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)。  
  
## <a name="see-also"></a>请参阅  
 [第 1 课：生成架构并创建消息](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)