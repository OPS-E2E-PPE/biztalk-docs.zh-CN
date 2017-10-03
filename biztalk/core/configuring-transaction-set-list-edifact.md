---
title: "配置事务集列表 (EDIFACT) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b03ace75-70bf-47c9-9a94-df813d7cab1e
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7f6b4d9a5aae6c8758d3a6d4f46d18f9a820fabd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-transaction-set-list-edifact"></a>配置事务集列表 (EDIFACT)
[!INCLUDE[prague](../includes/prague-md.md)] 使您可以定义在处理 EDI 交换时必须始终包括或排除的事务集列表。 本部分提供了有关如何创建事务集列表的说明。  
  
> [!IMPORTANT]
>  没有属性禁用此页上，即使你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-a-transaction-set-list"></a>配置事务集列表  
  
1.  创建 EDIFACT 编码协议中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。 若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**事务设置设置**部分中，单击**事务集列表**。  
  
3.  选择**支持事务集，从列表**选项如果你想要创建的必须始终最先处理的事务集的列表。  
  
    > [!NOTE]
    >  如果您通常收到具有特定事务类型的交换（比如 APERAK），则可以使用该选项。 在这种情况下，可以将该事务类型添加到列表中，以便不会处理其他类型的事务集。  
  
4.  选择**从列表中排除事务集**选项如果你想要创建的不会处理的事务集的列表。  
  
    > [!NOTE]
    >  如果您通常接收事务类型变化的交换，则可以使用此选项。 在这种情况下，您需要将这些事务类型添加到不获取任何事务集的列表。  
  
5.  单击中的空单元格**UNH2.1**列并从下拉列表中选择事务设置你想要排除上支持的类型。  
  
6.  若要从列表中删除事务类型，选择事务类型的行，然后单击**删除**。  
  
7.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置事务集设置 (EDIFACT)](../core/configuring-transaction-set-settings-edifact.md)