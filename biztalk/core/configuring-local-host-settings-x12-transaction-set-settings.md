---
title: 配置本地主机设置 （X12-事务集设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e31b41c3-49fc-46ef-ab69-889e30dfc58e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 897a8f5c9cacd84f8a54f06276c0170fba7045cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390835"
---
# <a name="configuring-local-host-settings-x12-transaction-set-settings"></a>配置本地主机设置（X 12-事务集设置）
若要处理传入的交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]必须确定它需要使用在处理和验证交换的架构。 这包括确定与架构相关联的目标命名空间并确定要使用的架构。 在参与方协议的此页上，输入要在确定目标命名空间时使用的属性。 如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]确定架构中，请参阅[协议解析、 架构发现和收到的 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)。  
  
> [!NOTE]
>  本主题还适用于与 HIPAA 相关的设置。  
  
> [!IMPORTANT]
>  没有属性上将禁用**参与方 A-> 参与方 B**单向协议选项卡，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**复选框为参与方 a。但是，禁用中相同页面上的所有属性**参与方 B-> 参与方 A**选项卡上，如果您创建参与方 A.时选中复选框  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
## <a name="determining-the-target-namespace"></a>确定目标 Namespace  
 在中**自定义目标命名空间**网格中，您可以设为目标命名空间的命名空间之一的标准架构附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 在网格中，将关联的值**目标 Namespace**使用的应用程序发送方的值的元素 (**GS2**) 和事务集标识符代码 (**ST1**)。 如果 BizTalk 接收一条消息的**GS2**并**ST1**数据元素与网格行中的匹配，BizTalk 将使用相应的命名空间来处理该消息。 您输入的元素的值必须是唯一的。  
  
 如果消息没有与匹配**GS2**并**ST1**网格中，BizTalk Server 的任何行中的数据元素将处理该消息的行中使用命名空间，为其**默认**列进行检查。 可用作默认目标命名空间。 如果未不标识任何命名空间，BizTalk Server 将使用的默认命名空间`http://schemas.microsoft.com/BizTalk/Edi/EDIFACT/2006`。  
  
> [!NOTE]
>  如果您在网格中，输入设置的任何字段，然后删除该设置，必须删除整行或该页的验证将失败。  
  
> [!NOTE]
>  有关使用此网格中，运行完成 EDI 接口开发人员教程，专门设置参与方接收的交换中的说明。 有关详细信息，请参阅[步骤 4:为您的贸易合作伙伴配置参与方和业务配置文件](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md)。  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a>若要配置本地主机设置为事务集  
  
1.  创建 X12 编码协议，如中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。 若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2.  在单向协议选项卡下**事务集设置**部分中，单击**本地主机设置**。  
  
3.  选择**将隐式小数格式 Nn 十进制数值**若要使用的中间 XML 中 BizTalk Server 的十进制数字值格式 Nn 指定的 EDI 数值转换。  
  
    > [!NOTE]
    >  在此转换后的中间 XML 可能无法通过长度验证。 这是因为采用以 10 为基数的数字格式的数字包含小数点，使其长度超过一个以 Nn 格式。 可以通过添加的值来解决此问题**1**为最小/最大长度值。  
  
4.  作为包含在事务集验证设置，如果将设置**尾部分隔符策略**到**可选**或**必需**，可以选择**创建空XML 标记为尾部分隔符**以使交换发送方包含为尾部分隔符的空 XML 标记。  
  
5.  在中**自定义目标 Namespace**部分中，执行以下操作：  
  
    1.  选择**默认**包含你想要定义的默认目标命名空间的行的复选框。  
  
    2.  在中**对于 ST1**列中，选择一个值为事务集标识符代码，从下拉列表。  
  
    3.  在中**GS2**列中，输入应用程序发送方与两个字符的最小值和最多包含 15 个字符的字母数字值。 这是必填字段。  
  
    4.  在中**目标 Namespace**列中，从下拉列表中选择或输入当网格的任意行中的数据元素与交换中的字段不存在任何匹配项时要使用的交换目标命名空间。  
  
        > [!NOTE]
        >  这些将是 BizTalk Server 将与它收到的交换关联的值进行比较的值。  
  
    5.  重复这些步骤的任何其他目标命名空间使用。  
  
    6.  若要从列表中删除目标命名空间，选择的行，然后单击**删除**。  
  
6.  单击**Apply**以接受更改，或单击**确定**以输入和验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置事务集设置 (X12)](../core/configuring-transaction-set-settings-x12.md)