---
title: 使用 Oracle E-business Suite 中配置事务隔离级别和事务超时 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: db3d64ad-037d-486a-bdde-45c8199613f1
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bbff645105feb4732afdf86aa3a591252c0d88c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969212"
---
# <a name="configure-transaction-isolation-level-and-transaction-timeout-with-oracle-e-business-suite"></a>使用 Oracle E-business Suite 中配置事务隔离级别和事务超时
执行 （轮询和通知） 的入站的操作时使用[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]与[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]，您应适当地配置事务隔离级别和事务超时值。 为此，请执行以下操作：  

1. 启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。  

2. 在控制台树中，展开**BizTalk 组**，然后展开**应用程序**。  

3. 生成元数据使用后已部署的 BizTalk 应用程序[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。  

4. 右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。  

5. 在中**接收端口属性**对话框中，在**常规**选项卡上，键入接收端口的名称。  

6. 在左窗格中**接收端口属性**对话框中，单击**接收位置**，然后单击**新建**在右窗格中，可以定义新的接收位置。  

7. 在中**接收位置属性**对话框中，单击**WCF 自定义**中**类型**列表。  

8. 单击**配置**相邻**类型**列表。  

9. 在中**Wcf-custom 传输属性**对话框中，单击**行为**选项卡。  

10. 在中**行为**列表中，右键单击**ServiceBehavior**，然后单击**将扩展添加**。  

11. 在中**选择行为扩展**对话框中，选择**oracleEBSAdapterInboundTransactionBehavior**，然后单击**确定**。  

12. 在左窗格中**Wcf-custom 传输属性**，选择**oracleEBSAdapterInboundTransactionBehavior**服务**ServiceBehavior**。  

13. 在右窗格中**Wcf-custom 传输属性**，指定相应的值**transactionIsolationLevel**并**transactionTimeout**参数。 可以选择任意下列事务隔离级别： **Serializable**， **RepeatableRead**， **ReadCommitted**， **ReadUncommitted**，**快照**，**混沌测试**，并且**未指定**。 有关这些事务隔离级别的信息，请参阅**成员**在部分[ http://go.microsoft.com/fwlink/?LinkId=126983 ](http://go.microsoft.com/fwlink/?LinkId=126983)。  

    > [!IMPORTANT]
    >  Oracle E-business Suite 支持仅以下两个事务隔离级别： ReadCommitted 和 Serializable。  

     ![设置事务隔离级别](../../adapters-and-accelerators/adapter-oracle-ebs/media/2bafbb9d-4daa-43c0-abcb-35220e6a3cb5.gif "2bafbb9d-4daa-43c0-abcb-35220e6a3cb5")  

14. 单击**确定**中**Wcf-custom 传输属性**对话框。  

15. 单击**确定**中打开的对话框以保存所做的更改。
