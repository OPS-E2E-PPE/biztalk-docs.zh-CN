---
title: "如何将跟踪的消息复制到跟踪数据库 BizTalk |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, copying between servers
- MessageBox database, Tracking database
- Tracking database, linking servers
- MessageBox database, copying messages
- linking, servers
- Tracking database, archiving
- archiving [Tracking database], linking servers
- Tracking database, MessageBox database
- Tracking database, copying messages
- archiving [Tracking database], MessageBox database
- MessageBox database, linking servers
- MessageBox database, archiving
ms.assetid: 369e972a-efbe-4ad5-a68f-aa3bbfb9ad54
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23aaa8e3bea3405d51a18da1778d420550ad4584
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-copy-tracked-messages-into-the-biztalk-tracking-database"></a>如何将跟踪的消息复制到跟踪数据库 BizTalk
存档和清除进程可能会访问和/或更新其他 SQL Server 中的数据库，因此必须在所涉及的 SQL Server 实例之间设置链接服务器。 可以使用链接服务器直接将跟踪的消息从 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库服务器复制到 BizTalk 跟踪 (BizTalkDTADb) 数据库中。 必须在以下项之间设置链接服务器：  
  
-   每个 BizTalk MessageBox (BizTalkMsgBoxDb) 数据库以及 BizTalk 跟踪 (BizTalkDTADb) 数据库。  
  
-   BizTalk 跟踪 (BizTalkDTADb) 数据库以及用于存档验证的验证服务器。  
  
-   BizTalk MessageBox (BizTalkMsgBoxDb) 数据库的宿主计算机上的 SQL Server 代理的服务帐户必须对链接服务器上的 BizTalk 跟踪 (BizTalkDTADb) 数据库具有 db_datareader 和 db_datawriter 权限。  
  
> [!NOTE]
>  在 SQL Server 代理中，验证复制作业能够正常运行，而不会产生任何错误。 否则，错误可能会阻止将数据移动到跟踪数据库中。  
  
## <a name="prerequisites"></a>先决条件  
 若要执行此过程，必须以 SQL Server sysadmin 固定服务器角色成员的帐户登录。  
  
### <a name="to-copy-tracked-messages-into-the-biztalk-tracking-database-sql-server-2008"></a>若要将跟踪的消息复制到 BizTalk 跟踪数据库 (SQL Server 2008)  
  
1.  单击**启动**，单击**所有程序**，单击**Microsoft SQL Server 2008 R2**，然后单击**SQL Server Management Studio**。  
  
2.  在**连接到服务器**对话框中，指定 BizTalk 跟踪 (BizTalkDTADb) 数据库所在的 SQL server 和适当的身份验证类型的名称，然后单击**连接**到连接到相应的 SQL server。  
  
3.  在**Microsoft SQL Server Management Studio**，双击**SQL Server 代理**，然后单击**作业**。  
  
4.  在细节窗格中，右键单击**TrackedMessages_Copy_BizTalkMsgBoxDb**，然后单击**属性**。  
  
5.  在**作业属性-TrackedMessages_Copy_BizTalkMsgBoxDb**对话框中，在**选择页**，单击**步骤**。  
  
6.  下**作业步骤列表**，单击**清除**，然后单击**编辑**。  
  
7.  在**命令**框中，编辑跟踪服务器和数据库名称参数视情况而定，然后单击**确定**。  
  
8.  上**作业属性-TrackedMessages_Copy_BizTalkMsgBoxDb**对话框中，在**选择页**，单击**常规**，选择**已启用**复选框，并依次**确定**。  
  
     消息将从 BizTalk MessageBox 数据库 (BizTalkMsgBoxDb) 复制到 BizTalk 跟踪数据库 (BizTalkDTADb)。  
  
> [!IMPORTANT]
>  如果添加新的 MessageBox 数据库，将需要为新的 MessageBox 数据库再执行一次此过程。  
  
## <a name="see-also"></a>另请参阅  
 [存档和清除 BizTalk 跟踪数据库](../core/archiving-and-purging-the-biztalk-tracking-database.md)