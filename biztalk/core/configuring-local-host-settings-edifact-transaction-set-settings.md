---
title: 配置本地主机设置 （EDIFACT-事务集设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f7c9cb9-7b4b-41de-a3f3-c0519b18673c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d918e422384a68875e2bf6625ca983c1819f1d61
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390928"
---
# <a name="configuring-local-host-settings-edifact-transaction-set-settings"></a>配置本地主机设置（EDIFACT-事务集设置）
若要处理传入的交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]必须确定它需要使用在处理和验证交换的架构。 这包括确定与架构相关联的目标命名空间并确定要使用的架构。 在参与方协议的此页上，输入要在确定目标命名空间时使用的属性。 BizTalk Server 如何确定架构中所述[协议解析、 架构发现和收到的 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)。  
  
> [!IMPORTANT]
>  没有属性上将禁用**参与方 A-> 参与方 B**单向协议选项卡，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**复选框为参与方 a。但是，禁用中相同页面上的所有属性**参与方 B-> 参与方 A**选项卡上，如果您创建参与方 A.时选中复选框  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
## <a name="determining-the-target-namespace"></a>确定目标 Namespace  
 在中**自定义目标 Namespace**网格中，可以将目标命名空间设置为与 Microsoft 一起提供的标准架构的命名空间之一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 在网格中，将关联的值**目标 Namespace**具有值的元素**UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**， **UNG2.1**，并**UNG2.2**元素。 如果 BizTalk 接收一条消息的**UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**， **UNG2.1**，和**UNG2.2**元素与网格行中匹配，BizTalk 将使用相应的命名空间来确定它将用于处理该消息的架构。 您输入的元素的值必须是唯一的。  
  
 如果消息没有与匹配**UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**， **UNG2.1**，并**UNG2.2**网格中，BizTalk Server 的任意行中的元素将处理该消息为其行中使用命名空间**默认**选中列。 可用作默认目标命名空间。 如果未不标识任何命名空间，BizTalk 将使用的默认命名空间`http://schemas.microsoft.com/BizTalk/Edi/Edifact/2006`。  
  
> [!NOTE]
>  如果您在网格中，输入设置的任何字段，然后删除该设置，必须删除整行或该页的验证将失败。  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a>若要配置本地主机设置为事务集  
  
1.  创建 EDIFACT 编码协议，如中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。 若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2.  在单向协议选项卡下**事务集设置**部分中，单击**本地主机设置**。  
  
3.  作为包含在事务集验证设置，如果将设置**尾部分隔符策略**到**可选**或**必需**，可以选择**创建空XML 标记为尾部分隔符**以使交换发送方包含为尾部分隔符的空 XML 标记。  
  
4.  选择**使用点 （.） 作为小数分隔符**启用 BizTalk Server 中包含点 （.） 包含十进制数的交换外创建的 XML 消息。  
  
5.  在中**自定义目标 Namespace**部分中，执行以下操作：  
  
    1.  选择**默认**包含你想要定义的默认目标命名空间的行的复选框。  
  
    2.  在中**UNH2.1**列中，指定消息类型。 （最多六个字符）。  
  
    3.  在中**UNH2.2**列中，指定消息版本号。 （最小值、 一个字符; 最多三个字符）。  
  
    4.  在中**UNH2.3**列中，指定消息发行版号。 （最小值、 一个字符; 最多三个字符）。  
  
    5.  在中**UNH2.5**列中，指定分配的代码。 （最多六个字符。 必须为字母数字）。  
  
    6.  在中**UNG2.1**列中，输入应用程序发件人的标识具有最少的一个字符，最多为 35 个字符的字母数字值。 此字段是必需的。  
  
    7.  在中**UNG2.2**列中，为最少一个字符，最多四个字符的应用程序发送方代码限定符输入一个字母数字值。 此字段是可选的。  
  
    8.  在中**目标 Namespace**列中，从下拉列表中选择或输入当网格的任意行中的数据元素与交换中的字段不存在任何匹配项时要使用的交换目标命名空间。  
  
        > [!NOTE]
        >  这些将是 BizTalk Server 将与它收到的交换关联的值进行比较的值。  
  
    9. 重复这些步骤的任何其他目标命名空间使用。  
  
    10. 若要从列表中删除目标命名空间，选择的行，然后单击**删除**。  
  
6.  单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置事务集设置 (EDIFACT)](../core/configuring-transaction-set-settings-edifact.md)