---
title: 步骤 8： 在 BTARN 数据库中查看消息 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, viewing
- loopback tutorial, viewing messages
- databases, viewing messages
ms.assetid: c549670c-4428-483c-906c-eff163ddef9a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 018bd2515dc2c363474c8058a861fd763cb73352
ms.sourcegitcommit: 436ebffd959a9c4bdaafd4da9a5843c59a018eb7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2018
ms.locfileid: "34855440"
---
# <a name="step-8-view-messages-in-the-btarn-databases"></a>BTARN 数据库中的步骤 8： 查看消息
在此步骤中，您将使用 SQL 查询分析器查看存储在 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 数据库中的业务线 (LOB) 消息，以检验您的环回方案是否正常运行。  
  
 LOB 应用程序实用工具生成 LOB 消息并将其提交到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 后，发起方（本组织）和响应方（合作伙伴）系统中将发生以下事件：  
  
 发起方工作流  
  
-   SubmitRNIF 将 LOB 消息提交到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] DATA 数据库的 MessagesFromLOB 表。  
  
-   SQL 适配器接收位置提取消息，并将其传送至 MessageBox 数据库。 SQL 适配器在运行 `GetMessagesFromLOB` 存储过程时一次提取一条消息。  
  
-   专用发起方从 MessageBox 数据库中提取消息，然后使用附加的已升级上下文属性将消息重新放到 MessageBox 数据库中。  
  
-   公用发起方根据订阅筛选器从 MessageBox 数据库中提取消息。  
  
-   HTTP 发送端口根据订阅利用 RNIFSend 管道提取消息。 它将消息保存到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Archive 数据库的 MessageStorageOut 表中，确保不可否认性，然后再将该消息发送至 RNIFSend.aspx 页。  
  
-   RNIFSend.aspx 页接收的 MIME 编码消息带有查询字符串变量，这些变量含有消息的最终目标，即合作伙伴组织的 URL。  
  
 响应方工作流  
  
-   [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将 RNIF 消息发送到 RNIFReceive.aspx 页，MIME 解码包装程序在该页上被删除。 消息被标识为同步或异步，然后转发到同步接收位置或异步接收位置（RNIF_Sync_Receive 或 RNIF_Async_Receive）。  
  
-   HTTP 接收位置首先将消息的线路格式保存到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Archive 数据库的 MessageStorageIn 表中，确保不可否认性。 HTTP 接收位置然后进行解码、解密（对于 RNIF 2.0）、验证消息签名、拆装 XML 消息各部分、根据签名进行授权，最后使用正确的已升级属性将消息放到 MessageBox 数据库中  
  
-   公用响应方根据订阅提取消息各部分，然后根据正确的 RNIF 标准验证和处理消息。 服务内容部分使用正确的上下文属性将消息放到 MessageBox 数据库中。  
  
-   SQL 发送端口根据订阅筛选器提取消息。 然后将消息保存到 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] DATA 数据库的 MessagesToLOB 表中。  
  
> [!NOTE]
>  在响应方端中，公共响应方负责生成确认接收或返回到发起方的异常信号。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 不保存信号消息 MessagesFromLOB 表中。 这是因为 LOB 应用程序不生成信号消息。 操作消息将继续通过专用响应方，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将操作消息保存到 MessagesToLOB 表中。  
  
> [!NOTE]
>  对于双操作 Pip 在响应方端 LOB 负责生成响应消息。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将它放置于 MessagesFromLOB 表，以便通过与发起方端过程相同的进程。 在这种情况下，发起方方面的公用发起方流程将返回响应消息的确认回执或异常信号。  
  
### <a name="to-view-messages-in-the-btarn-databases"></a>在 BTARN 数据库中查看消息  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft SQL Server\<版本\>**，然后单击**SQL ServerManagement Studio**。  
  
2.  在连接到服务器对话框中，单击**连接**。  
  
    > [!NOTE]
    >  在“对象资源管理器”窗格中，检验 SQL Server 代理是否已启动。 如果没有，请右键单击**SQL Server 代理**，然后单击**启动**。  
  
3.  在 Microsoft SQL Server Management Studio 中，单击**新查询**。  
  
4.  在“空查询”窗口中，键入以下内容：  
  
    ```  
    use BTARNArchive  
    SELECT * FROM         MessageStorageIn ORDER BY TIMECREATED ASC  
    SELECT * FROM         MessageStorageOut ORDER BY TIMECREATED ASC  
  
    use BTARNData  
    SELECT     * FROM         MessagesFromLOB ORDER BY TIMECREATED ASC  
    SELECT     * FROM         MessagesToLOB ORDER BY TIMECREATED ASC  
    SELECT     * FROM         Attachments ORDER BY TIMECREATED ASC  
    ```  
  
5.  在 Microsoft SQL Server Management Studio 中，单击**执行**。  
  
 您将在 MessagesFromLOB 表中看到一条操作消息，如果几分钟后（此时间取决于您的系统配置）再次运行查询，您将在 MessagesToLOB 表中看到所生成的两条消息，其 MessageCategory 值分别为 AsyncAckSignal (25) 和 AsyncAction (10)。  
  
## <a name="see-also"></a>请参阅  
 [环回](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md)   
 [Loopback 教程](../../adapters-and-accelerators/accelerator-rosettanet/loopback-tutorial.md)
