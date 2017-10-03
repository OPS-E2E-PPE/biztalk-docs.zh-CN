---
title: "使用 SQL 配置事务隔离级别和事务超时 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 55355272-60c0-49e4-b37e-9198458ab305
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e75d63118c24602439434c9c7ba281fa9cbc7805
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-transaction-isolation-level-and-transaction-timeout-with-sql"></a>使用 SQL 配置事务隔离级别和事务超时
执行 （轮询和通知） 的入站的操作时使用[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，你应适当地配置事务的隔离级别和事务超时值。 为此，请执行以下操作：  
  
1.  启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  
  
2.  在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。  
  
3.  展开你想要部署的应用程序[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。  
  
4.  右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。  
  
5.  在**接收端口属性**对话框中，在**常规**选项卡上，键入接收端口的名称。  
  
6.  在左窗格中**接收端口属性**对话框中，单击**接收位置**，然后单击**新建**在右窗格中可以定义新接收位置。  
  
7.  在**接收位置属性**对话框中，单击**WCF 自定义**中**类型**列表。  
  
8.  单击**配置**靠近**类型**列表。  
  
9. 在**WCF 自定义传输属性**对话框中，单击**行为**选项卡。  
  
10. 在**行为**列表中，右键单击**ServiceBehavior**，然后单击**将扩展添加**。  
  
11. 在**选择行为扩展**对话框中，选择**sqlAdapterInboundTransactionBehavior**，然后单击**确定**。  
  
12. 在左窗格中**WCF 自定义传输属性**，选择**sqlAdapterInboundTransactionBehavior**服务下**ServiceBehavior**。 用于接收 （入站的操作消息），用户可以使用 sqlAdapterInboundTransactionBehavior 控制的隔离级别和默认值是**ReadCommitted**。  
  
13. 在右窗格中**WCF 自定义传输属性**，指定适当的值为**transactionIsolationLevel**和**transactionTimeout**参数。 您可以选择任一以下事务隔离级别： **Serializable**， **RepeatableRead**， **ReadCommitted**， **ReadUncommitted**，**快照**，**混沌**，和**未指定**。  
  
    > [!NOTE]
    >  事务隔离级别的默认值是**Serializable**为入站和出站操作 WCF SQL 适配器。 有关这些事务隔离级别的信息，请参阅**成员**部分[隔离级别枚举](http://go.microsoft.com/fwlink/?LinkId=126983)(http://go.microsoft.com/fwlink/?LinkId=126983)。  
  
     ![将事务隔离级别，设置](../../adapters-and-accelerators/adapter-sql/media/b39c180e-ca9f-48ca-9550-f4837826d00e.gif "b39c180e-ca9f-48ca-9550-f4837826d00e")  
  
14. 单击**确定**中**WCF 自定义传输属性**对话框。  
  
15. 单击**确定**中打开对话框以保存所做的更改。