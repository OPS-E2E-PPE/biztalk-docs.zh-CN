---
title: "配置发送端口关联 (EDIFACT) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d7faabc7-072c-408c-bbd5-f0a039be81f8
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 629bde13f8edc9074b3e6bcb4741746e3de8e1a6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="configuring-send-port-association-edifact"></a>配置发送端口关联（EDIFACT）
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用发送端口关联来解析传出 EDI 交换的协议。 通过匹配订阅该消息的发送端口与协议关联的发送端口，将 EDI 交换解析为协议。 本主题提供有关如何将发送端口与协议相关联的说明。  
  
> [!NOTE]
>  如果同一发送端口与多个协议关联，BizTalk Server 将生成错误。  
  
> [!IMPORTANT]
>  在 BizTalk Server 中，仅在协议级别完成发送端口关联。 但是，在 BizTalk Server 2009 中，发送端口与参与方级别关联。 为了向后兼容，**发送端口**都还可以使用页面的参与方属性一部分 (请参阅[配置常规参与方属性](../core/configuring-general-party-properties.md))。 每当您将发送端口与协议相关联时，发送端口设置也会传播到参与方设置，您同时会在此页面上看到发送端口关联。 但是，反之则不然。 不能将发送端口与参与方关联，然后使该发送端口自动作为协议设置的一部分使用。  
  
> [!IMPORTANT]
>  发送端口关联网格禁用此页上，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。  
>   
>  仅在与参与方所发送交换的属性对应的单向协议选项卡上禁用该网格。 例如，如果创建两个参与方 A 方和方 B，并且对于方 A，清除复选框，则网格禁用上**A 方-> 方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-associate-send-ports-with-an-agreement"></a>将发送端口与协议相关联  
  
1.  创建 EDIFACT 编码协议中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。 若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**交换设置**部分中，单击**发送端口**。  
  
3.  单击下面的空单元格中**名称**列，然后从下拉列表中，选择要将与协议相关联的发送端口。 **URI**列将显示发送端口地址。  
  
4.  若要删除发送端口关联，请选择发送端口的行，然后单击**删除**。  
  
5.  若要查看发送端口属性，请选择发送端口的行，然后单击**属性**。  
  
6.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置交换设置 (EDIFACT)](../core/configuring-interchange-settings-edifact.md)