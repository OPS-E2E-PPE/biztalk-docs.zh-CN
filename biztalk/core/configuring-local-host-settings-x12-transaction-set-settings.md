---
title: "配置本地主机设置 （X12 事务集设置） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e31b41c3-49fc-46ef-ab69-889e30dfc58e
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fcc099535e6a7b96c5c4bbdd29112da46af3522
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-local-host-settings-x12-transaction-set-settings"></a>配置本地主机设置（X 12-事务集设置）
为了处理传入的交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 必须确定在处理和验证交换时需要使用的架构。 这包括确定与架构关联的目标命名空间和确定要使用的架构。 在参与方协议的此页中，可输入要在确定目标命名空间时使用的属性。 如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]确定架构所述[协议解析、 架构发现和接收 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)。  
  
> [!NOTE]
>  本主题还适用于与 HIPAA 相关的设置。  
  
> [!IMPORTANT]
>  没有属性上将禁用**A 方-> 方 B**单向协议选项卡，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**复选框当事方 a。但是，将所有属性都禁用中相同页面上**B 方-> A 方**选项卡上，如果创建 a 方。 时选中复选框  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
## <a name="determining-the-target-namespace"></a>确定目标命名空间  
 在**自定义目标命名空间**网格中，你可以设置的目标命名空间为某个命名空间为标准架构附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 在网格中，你将关联的值**目标 Namespace**与应用程序发件人的值的元素 (**GS2**) 和事务集标识符代码 (**ST1**)。 当 BizTalk 收到一条消息其**GS2**和**ST1**数据元素与匹配的行的网格中，BizTalk 将使用相应的命名空间来处理该消息。 输入的元素的值必须是唯一的。  
  
 如果消息没有包含的匹配项**GS2**和**ST1**任何行网格中，BizTalk Server 中的数据元素将处理该消息为其行中使用命名空间**默认**列进行检查。 可以作为默认目标命名空间。 如果没有标识命名空间，BizTalk Server 将使用 `http://schemas.microsoft.com/BizTalk/Edi/EDIFACT/2006` 的默认命名空间。  
  
> [!NOTE]
>  如果为网格中的任意字段输入设置，然后删除该设置，则必须删除整行，否则对该页的验证将失败。  
  
> [!NOTE]
>  有关如何使用此网格的说明，请完成 EDI 接口开发人员教程，尤其是有关对参与方进行设置以接收交换的部分。 有关详细信息，请参阅[步骤 4： 为你的贸易合作伙伴配置方和业务配置文件](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md)。  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a>要配置事务集的本地主机设置，请执行以下操作：  
  
1.  创建 X12 编码协议中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。 若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**事务设置设置**部分中，单击**本地主机设置**。  
  
3.  选择**转换隐式小数格式 Nn 以十进制数值**将使用格式 Nn 转换为 BizTalk Server 中的中间 XML 中的以 10 为基数的数字值指定的 EDI 数字转换。  
  
    > [!NOTE]
    >  在此转换后，中间 XML 可能无法通过长度验证。 这是因为十进制数值格式的数包含小数点，使其比 Nn 格式的数长一位。 你可以通过添加的值来解决此问题**1**到的最小/最大长度值。  
  
4.  因为该事务的一部分设置验证设置，如果你设置**尾随分隔符策略**到**可选**或**必需**，你可以选择**创建空XML 标记为尾随分隔符**能够包含的尾随分隔符的空 XML 标记交换发件人。  
  
5.  在**自定义目标 Namespace**部分中，执行以下操作：  
  
    1.  选择**默认**包含你想要定义的默认目标命名空间的行的复选框。  
  
    2.  在**为 ST1**列中，选择一个值用于将事务从下拉列表设置标识符代码。  
  
    3.  在**GS2**列中，该应用程序发件人不少于两个字符，最多包含 15 个字符输入一个字母数字值。 这是必填字段。  
  
    4.  在**目标 Namespace**列中，从下拉列表中选择或输入要网格的任何行中的数据元素和交换中的字段之间未不找到任何匹配时使用的交换的目标命名空间。  
  
        > [!NOTE]
        >  BizTalk Server 会将这些值与它所收到的交换的关联值进行比较。  
  
    5.  对任何其他要使用的目标命名空间，重复这些步骤，  
  
    6.  若要从列表中删除目标命名空间，请选择行，然后单击**删除**。  
  
6.  单击**应用**接受所做的更改，或单击**确定**以输入和验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置事务集设置 (X12)](../core/configuring-transaction-set-settings-x12.md)