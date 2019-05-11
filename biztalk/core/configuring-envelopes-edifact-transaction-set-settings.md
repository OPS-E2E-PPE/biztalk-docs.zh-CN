---
title: 配置信封 （EDIFACT-事务集设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec140def-6155-4b8a-8489-6e0a530bd697
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c62b963042c7a4f5ea141dd44faa4f914c30f22
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391299"
---
# <a name="configuring-envelopes-edifact-transaction-set-settings"></a>配置信封（EDIFACT--事务集设置）
在中**信封**页**事务集设置**部分中，可以定义 BizTalk Server 如何生成它发送到参与方的 EDIFACT 编码交换的 UNG 和 UNH 段。  
  
 UNG 段是标识和指定的 EDIFACT 编码交换的功能组标头。 它包含有关日期和时间功能组已准备好的以及类型和版本功能组中的文档的信息。  
  
 UNH 段是交换的 EDIFACT 编码的消息标头段。 它提供有关消息类型，以及负责维护消息类型的发布的机构的信息。 此段指示交换和文档后面的类型中的文档的开头。  
  
 在中**功能组标头 (UNG)** 部分中，你将关联**UNG**值替换**UNH**值和命名空间。 BizTalk Server 确定某一 BizTalk XML 消息已设置的值**UNH**元素并**目标命名空间**网格的行，在 BizTalk Server 将填充**UNG**网格的同一行中的值的数据元素。 值**UNH**元素并**目标命名空间**必须是唯一的。  
  
 如果消息没有与匹配**UNH**元素并**目标命名空间**BizTalk Server 将在任何行中填充该消息的值**UNG**默认行中的元素。 将使用这些值，即使该消息没有与匹配**UNH**元素并**目标命名空间**默认行。  
  
 在 BizTalk 引擎确定某一 BizTalk XML 消息具有为 UNH 元素和目标命名空间设置的值，引擎将在网格中，提供为其设置的值填充消息中的 UNG 元素**创建分组段**选中复选框。  
  
> [!NOTE]
>  在中**功能组标头 (UNG)** 部分中，如果您在网格中，输入设置的任何字段，然后再删除该设置，必须删除整行或该页的验证将失败。  
  
> [!IMPORTANT]
>  所有属性上将都禁用**参与方 A-> 参与方 B**单向协议选项卡，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**检查参与方 a 的框但是，所有属性都在同一页面上将都启用**参与方 B-> 参与方 A**选项卡上，如果您创建参与方 A.时选中复选框  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-define-the-ung-and-unh-segments"></a>定义 UNG 和 UNH 段  
  
1.  创建 EDIFACT 编码协议，如中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。 若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2.  在单向协议选项卡下**事务集设置**部分中，单击**信封**。  
  
3.  在网格的行中，输入以下值：  
  
    -   在中**对于消息类型 UNH2.1**列中，输入事务集类型。 （最多六个字符）。  
  
    -   在中**UNH2.2**列中，输入消息版本号。 （最小值、 一个字符; 最多三个字符）。  
  
    -   在中**UNH2.3**列中，输入消息发行版号。 （最小值、 一个字符; 最多三个字符）。  
  
    -   在中**UNH2.5**列中，输入分配的代码。 （最多六个字符。 必须为字母数字）。  
  
    -   在中**目标命名空间**列中，选择架构的目标命名空间。 这是必填字段。  
  
        > [!NOTE]
        >  这些将是 BizTalk Server 将与生成的交换关联的值进行比较的值。  
  
4.  在网格的同一行中，输入以下值：  
  
    -   有关**UNG1** （功能组标识） 输入包含最少一个字符，最多为 6 个字符的字母数字值。 这是必填字段。  
  
    -   有关**UNG2.1** （应用程序发送方标识） 输入包含最少一个字符，最多为 35 个字符的字母数字值。 这是必填字段。  
  
    -   有关**UNG2.2** （应用程序发送方代码限定符） 输入包含最多四个字符的字母数字值。 这是一个可选字段。  
  
    -   有关**UNG3.1** （应用程序收件人标识），输入包含最少一个字符，最多为 35 个字符的字母数字值。 这是必填字段。  
  
    -   有关**UNG3.2** （应用程序接收方代码限定符） 输入包含最多四个字符的字母数字值。 这是一个可选字段。  
  
    -   有关**UNG6** （控制代理） 输入包含最少一个、 两个最多的字母数字值。 这是必填字段。  
  
    -   有关**UNG7.1** （消息类型版本号），输入包含最少一个字符，最多包含三个字符的字母数字值。 这是必填字段。  
  
    -   有关**UNG7.2** （消息类型发行版号） 输入包含最少一个字符，最多包含三个字符的字母数字值。 这是必填字段。  
  
    -   有关**UNG7.3** （协会分配代码），输入一个最少为 1 个字符，最多为 6 个字符的字母数字值。 这是必填字段。  
  
    -   有关**UNG8** （应用程序密码），输入包含最少一个字符，最多为 14 个字符的字母数字值。 这是必填字段。  
  
        > [!NOTE]
        >  这些将是 BizTalk Server 将在生成如果该交换的 UNG 字段中输入的值**对于消息类型 UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**，并**目标命名空间**同一行中的元素是那些与交换关联的匹配项。  
  
5.  重复步骤 4 和 5 在网格中输入其他行。  
  
6.  在网格中的一个行，请单击**默认**以将其指定为默认行。  
  
    > [!NOTE]
    >  如果消息没有与匹配**UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**，和**目标命名空间**在任何行，BizTalk Server 中的元素将填充该消息的值**UNG1**， **UNG2.1**， **UNG2.2**， **UNG3.1**， **UNG3.2**， **UNG6**， **UNG7.1**， **UNG7.2**， **UNG7.3**，并**UNG8**默认行中的元素。 将使用这些值，即使该消息没有与匹配**对于消息类型 UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**，并**目标命名空间**默认行中的元素。  
  
    > [!NOTE]
    >  如果选择没有默认的行，并且消息不具有的匹配项**UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**，和**目标命名空间**元素在任何行中，BizTalk 将挂起该消息。  
  
7.  单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置事务集设置 (EDIFACT)](../core/configuring-transaction-set-settings-edifact.md)