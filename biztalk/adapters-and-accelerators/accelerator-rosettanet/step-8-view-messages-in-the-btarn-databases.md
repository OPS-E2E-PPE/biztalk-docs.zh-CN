---
title: 步骤 8：在 BTARN 数据库中查看消息 |Microsoft Docs
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
ms.openlocfilehash: 94f9b676c2f8ea8c212a4ded6f50ee9037cad6ea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280545"
---
# <a name="step-8-view-messages-in-the-btarn-databases"></a>步骤 8：在 BTARN 数据库中查看消息
在此步骤中，您使用 SQL 查询分析器来查看业务 (LOB) 消息存储在 Microsoft®[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]数据库来验证环回方案是否正常工作。  
  
 LOB 应用程序后实用工具生成 LOB 消息并将其提交到[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]，发起方 （家庭） 和响应方 （合作伙伴） 将发生以下事件：  
  
 发起方工作流  
  
- SubmitRNIF 将 LOB 消息到 MessagesFromLOB 表的提交[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]数据数据库。  
  
- SQL 适配器接收位置从其中提取消息并将其传送到 MessageBox 数据库。 SQL 适配器提取一条消息在时间运行`GetMessagesFromLOB`存储过程。  
  
- 专用发起方会选取该消息从 MessageBox 数据库，然后再次将它放到 MessageBox 数据库与其他已升级的上下文属性。  
  
- 公用发起方会选取该消息从 MessageBox 数据库根据订阅筛选器。  
  
- HTTP 发送端口提取消息利用 RNIFSend 管道根据订阅。 将消息保存在 MessageStorageOut 表中[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不可否认性的存档数据库，然后将该消息发送至 RNIFSend.aspx 页。  
  
- RNIFSend.aspx 页接收查询字符串变量，包括消息 (合作伙伴组织的 URL) 的最终目标的 MIME 编码消息。  
  
  响应方工作流  
  
- [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将 RNIF 消息发送到 RNIFReceive.aspx 页删除 MIME 解码包装器的情况。 消息被标识为同步或异步的然后转发到同步或异步接收位置 （RNIF_Sync_Receive 或 RNIF_Async_Receive）。  
  
- HTTP 的不可否认的 MessageStorageIn 表中接收位置的第一个保存消息的传输格式[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]存档数据库。 HTTP 接收位置然后进行解码、 解密 （对于 RNIF 2.0) 中，验证其签名、 拆装 XML 消息部分、 授权基于该签名，然后将其放入 MessageBox 数据库具有正确的升级属性  
  
- 公用响应方选择消息部分基于订阅，然后验证并根据正确的 RNIF 标准对消息进行处理。 服务内容部分会将消息放到 MessageBox 数据库中具有正确的上下文属性。  
  
- SQL 发送端口提取消息根据订阅筛选器。 它然后将该消息保存在 MessagesToLOB 表中的[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]数据数据库。  
  
> [!NOTE]
>  响应方各，公用响应方负责生成的确认回执或异常信号回发起方。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 不保存在 MessagesFromLOB 表中的信号消息。 这是因为 LOB 应用程序不会生成信号消息。 操作消息将继续通过专用响应方，和[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将其保存到 MessagesToLOB 表。  
> 
> [!NOTE]
>  对于双操作 Pip，响应方各 LOB 负责生成响应消息。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将其放到 MessagesFromLOB 表中通过发起方流程与相同的进程。 在这种情况下，发起方公用发起方流程发回响应消息的确认回执或异常信号。  
  
### <a name="to-view-messages-in-the-btarn-databases"></a>在 BTARN 数据库中查看消息  
  
1. 单击**启动**，依次指向**所有程序**，指向**Microsoft SQL Server\<版本\>**，然后单击**SQL ServerManagement Studio**。  
  
2. 在连接到服务器对话框中，单击**Connect**。  
  
   > [!NOTE]
   >  在对象资源管理器窗格中，验证 SQL Server 代理已启动。 如果没有，请右键单击**SQL Server 代理**，然后单击**启动**。  
  
3. 在 Microsoft SQL Server Management Studio 中，单击**新查询**。  
  
4. 在空白查询窗口中，键入以下命令：  
  
   ```  
   use BTARNArchive  
   SELECT * FROM         MessageStorageIn ORDER BY TIMECREATED ASC  
   SELECT * FROM         MessageStorageOut ORDER BY TIMECREATED ASC  
  
   use BTARNData  
   SELECT     * FROM         MessagesFromLOB ORDER BY TIMECREATED ASC  
   SELECT     * FROM         MessagesToLOB ORDER BY TIMECREATED ASC  
   SELECT     * FROM         Attachments ORDER BY TIMECREATED ASC  
   ```  
  
5. 在 Microsoft SQL Server Management Studio 中，单击**Execute**。  
  
   您将看到在 MessagesFromLOB 表中，操作消息，如果在几分钟时间 （时间可能因您的系统配置） 再次运行查询，您将看到在 MessagesToLOB 表中的其 MessageCategory 值生成的两条消息AsyncAckSignal (25) 和 AsyncAction (10)。  
  
## <a name="see-also"></a>请参阅  
 [Loopback](../../adapters-and-accelerators/accelerator-rosettanet/loopback.md)   
 [Loopback 教程](../../adapters-and-accelerators/accelerator-rosettanet/loopback-tutorial.md)
