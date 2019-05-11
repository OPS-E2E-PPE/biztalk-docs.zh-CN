---
title: 配置发送端口关联 (EDIFACT) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7faabc7-072c-408c-bbd5-f0a039be81f8
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4762af77250eaf17624e643f62e0214953ca4118
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390769"
---
# <a name="configuring-send-port-association-edifact"></a>配置发送端口关联 (EDIFACT)
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用发送端口关联来解析传出 EDI 交换的协议。 EDI 交换解析为协议通过匹配订阅消息的发送端口与协议关联的发送端口。 本主题提供有关如何将相关联的说明将发送端口与协议。  
  
> [!NOTE]
>  如果同一发送端口与多个协议关联，BizTalk Server 将生成错误。  
  
> [!IMPORTANT]
>  在 BizTalk Server 发送端口关联仅在协议级别完成。 但是，在 BizTalk Server 2009 中，发送端口都关联参与方级别。 为了向后兼容**发送端口**页也是可用的参与方属性一部分 (请参阅[配置常规参与方属性](../core/configuring-general-party-properties.md))。 每当将发送端口与协议相关联，也会发送端口设置传播到参与方设置，您可以看到这个页面中的发送端口关联。 但是，反之不成立。 不能将发送端口与参与方相关联，然后使自动提供该发送端口作为协议设置的一部分。  
  
> [!IMPORTANT]
>  发送端口关联网格禁用此页上，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。  
>   
>  仅在与参与方所发送交换的属性相对应的单向协议选项卡上禁用该网格。 例如，如果您创建两个参与方 Party A 和参与方 B，并且对于参与方 A 清除该复选框，网格时禁用了**参与方 A-> 参与方 B**单向协议选项卡。  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-associate-send-ports-with-an-agreement"></a>若要将发送端口与协议相关联  
  
1.  创建 EDIFACT 编码协议，如中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。 若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2.  在单向协议选项卡下**交换设置**部分中，单击**发送端口**。  
  
3.  单击下的空单元格**名称**列，然后从下拉列表中，选择要将与协议相关联的发送端口。 **URI**列将显示发送端口地址。  
  
4.  若要删除发送端口关联，请选择发送端口的行，然后单击**删除**。  
  
5.  若要查看为发送端口属性，请选择发送端口的行，然后单击**属性**。  
  
6.  单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置交换设置 (EDIFACT)](../core/configuring-interchange-settings-edifact.md)