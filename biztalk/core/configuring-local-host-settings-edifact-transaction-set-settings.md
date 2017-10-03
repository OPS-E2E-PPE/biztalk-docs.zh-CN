---
title: "配置本地主机设置 （EDIFACT 事务集设置） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f7c9cb9-7b4b-41de-a3f3-c0519b18673c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 912af3a047f77f077bf9de58a25802f3c658e6b0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-local-host-settings-edifact-transaction-set-settings"></a>配置本地主机设置（EDIFACT-事务集设置）
为了处理传入的交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 必须确定在处理和验证交换时需要使用的架构。 这包括确定与架构关联的目标命名空间和确定要使用的架构。 在参与方协议的此页中，可输入要在确定目标命名空间时使用的属性。 中所述 BizTalk Server 如何确定架构[协议解析、 架构发现和接收 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)。  
  
> [!IMPORTANT]
>  没有属性上将禁用**A 方-> 方 B**单向协议选项卡，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**复选框当事方 a。但是，将所有属性都禁用中相同页面上**B 方-> A 方**选项卡上，如果创建 a 方。 时选中复选框  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
## <a name="determining-the-target-namespace"></a>确定目标命名空间  
 在**自定义目标 Namespace**网格中，可以将目标命名空间设置为随 Microsoft 提供的标准架构命名空间之一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 在网格中，你将关联的值**目标 Namespace**具有值的元素**UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**， **UNG2.1**，和**UNG2.2**元素。 当 BizTalk 收到一条消息其**UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**， **UNG2.1**，和**UNG2.2**元素匹配的行的网格中，BizTalk 将使用相应的命名空间来确定它将用于处理消息的架构。 输入的元素的值必须是唯一的。  
  
 如果消息没有包含的匹配项**UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**， **UNG2.1**，和**UNG2.2**任何行网格中，BizTalk Server 中的元素将处理该消息为其行中使用命名空间**默认**列进行检查。 可以作为默认目标命名空间。 如果未标识命名空间，则 BizTalk 将使用 `http://schemas.microsoft.com/BizTalk/Edi/Edifact/2006` 的默认命名空间。  
  
> [!NOTE]
>  如果为网格中的任意字段输入设置，然后删除该设置，则必须删除整行，否则对该页的验证将失败。  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a>要配置事务集的本地主机设置，请执行以下操作：  
  
1.  创建 EDIFACT 编码协议中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。 若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**事务设置设置**部分中，单击**本地主机设置**。  
  
3.  因为该事务的一部分设置验证设置，如果你设置**尾随分隔符策略**到**可选**或**必需**，你可以选择**创建空XML 标记为尾随分隔符**能够包含的尾随分隔符的空 XML 标记交换发件人。  
  
4.  选择**使用点 （.） 作为小数分隔符**若要启用 BizTalk Server 包括句点 （.） 中包含的小数的交换创建的 XML 消息。  
  
5.  在**自定义目标 Namespace**部分中，执行以下操作：  
  
    1.  选择**默认**包含你想要定义的默认目标命名空间的行的复选框。  
  
    2.  在**UNH2.1**列中，指定消息类型。 （最多六个字符）。  
  
    3.  在**UNH2.2**列中，指定消息的版本号。 （最小值、 一个字符; 最多三个字符）。  
  
    4.  在**UNH2.3**列中，指定消息发行版号。 （最小值、 一个字符; 最多三个字符）。  
  
    5.  在**UNH2.5**列中，指定所分配的代码。 （最多六个字符。 必须为字母数字值）。  
  
    6.  在**UNG2.1**列中，输入应用程序发件人的标识具有最少的一个字符，最多 35 个字符的字母数字值。 此字段为必填字段。  
  
    7.  在**UNG2.2**列中，输入最少包含一个字符，最多四个字符的应用程序发件人代码限定符的字母数字值。 此字段是可选的。  
  
    8.  在**目标 Namespace**列中，从下拉列表中选择或输入要网格的任何行中的数据元素和交换中的字段之间未不找到任何匹配时使用的交换的目标命名空间。  
  
        > [!NOTE]
        >  BizTalk Server 会将这些值与它所收到的交换的关联值进行比较。  
  
    9. 对任何其他要使用的目标命名空间，重复这些步骤，  
  
    10. 若要从列表中删除目标命名空间，请选择行，然后单击**删除**。  
  
6.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置事务集设置 (EDIFACT)](../core/configuring-transaction-set-settings-edifact.md)