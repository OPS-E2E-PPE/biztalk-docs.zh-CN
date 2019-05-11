---
title: 配置信封 （X12-事务集设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9313a7b9-72fa-4071-8c65-007371643179
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b478f566301e01fa26d1d72e8eadf80caafa9e7d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391271"
---
# <a name="configuring-envelopes-x12-transaction-set-settings"></a>配置信封（X12--事务集设置）
在中**信封**页**事务集设置**部分中，可以定义 BizTalk Server 如何生成它发送到参与方的 X12 编码交换的 GS 和 ST 段。 GS 段标识，并指定功能组对于 X12 编码的交换。 ST 段是 X12 编码交换的消息标头。  
  
 在此页上，将关联的值**GS1**， **GS2**， **GS3**， **GS4**， **GS5**， **GS7**，并**GS8**值的数据元素**事务类型**，**版本/发行版**，和**目标命名空间**数据元素。 当 BizTalk 确定某一 BizTalk XML 消息已设置的值**事务类型**，**版本/发行版**，并**目标命名空间**网格中的某一行中的元素BizTalk 将填充**GS1**， **GS2**， **GS3**， **GS4**， **GS5**， **GS7**，并**GS8**传出的信封中的数据元素交换网格的同一行中的值。 值**事务类型**，**版本/发行版**，并**目标命名空间**元素必须是唯一的。  
  
> [!NOTE]
>  如果您在网格中，输入设置的任何字段，然后删除该设置，必须删除整行或该页的验证将失败。  
  
> [!NOTE]
>  本主题还适用于与 HIPAA 相关的设置。  
  
> [!IMPORTANT]
>  所有属性上将都禁用**参与方 A-> 参与方 B**单向协议选项卡，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**检查参与方 a 的框但是，所有属性都在同一页面上将都启用**参与方 B-> 参与方 A**选项卡上，如果您创建参与方 A.时选中复选框  
  
## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  
  
### <a name="to-define-the-gs-and-st-segments"></a>定义 GS 和 ST 段  
  
1.  创建 X12 编码协议，如中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。 若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。  
  
2.  在单向协议选项卡下**事务集设置**部分中，单击**信封**。  
  
3.  在网格的行中，输入以下信息：  
  
    -   有关**事务类型**字段中，为事务集标识符代码，从下拉列表中选择一个值。  
  
    -   有关**版本/发行版**，输入包含最少一个字符，最多为 12 个字符的字母数字值。  
  
    -   有关**目标命名空间**元素，从下拉列表中，选择一个值，或输入一个命名空间。  
  
        > [!NOTE]
        >  这些将是 BizTalk Server 将与生成的交换关联的值进行比较的值。  
  
4.  在网格的同一行中，输入以下信息：  
  
    -   有关**GS1**，从下拉列表中选择的值为功能代码。 这是一个可选字段。  
  
    -   有关**GS2**，为两个字符的最小值和最多 15 个字符的应用程序发送方输入的字母数字值。 这是必填字段。  
  
    -   有关**GS3**，输入应用程序接收方最少包含 2 个字符，最多包含 15 个字符的字母数字值。 这是必填字段。  
  
    -   有关**GS4**，选择**CCYYMMDD**或**YYMMDD**。 这是一个可选字段  
  
    -   有关**GS5**，选择**HHMM**， **HHMMSS**，或者**HHMMSSdd**。 这是一个可选字段  
  
    -   有关**GS7**，从下拉列表中选择负责代理的值。 这是一个可选字段。  
  
    -   有关**GS8**，标识最少一个字符，最多为 12 个字符的文档中输入的字母数字值。 这是一个可选字段。  
  
        > [!NOTE]
        >  这些将是 BizTalk Server 将在生成如果该交换的 GS 字段中输入的值**事务类型**，**版本/发行版**，和**目标命名空间**同一行中的元素是那些与交换关联的匹配项。  
  
5.  重复步骤 3 和 4 网格中输入其他行。  
  
6.  在网格中的一个行，请单击**默认**以将其指定为默认行。  
  
    > [!NOTE]
    >  如果消息没有与匹配**事务类型**，**版本/发行版**，并**目标命名空间**在任何行，BizTalk Server 中的元素将填充该消息替换为值**GS1**， **GS2**， **GS3**， **GS5**， **GS7**，和**GS8**默认行中的元素。 将使用这些值，即使该消息没有与匹配**事务类型**，**版本/发行版**，并**目标命名空间**默认行中的元素。  
  
    > [!NOTE]
    >  如果没有默认值为所选的传入文档的不匹配**事务类型**，**版本/发行版**，并**目标命名空间**的任何行的元素将被挂起.  
  
7.  单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>请参阅  
 [配置事务集设置 (X12)](../core/configuring-transaction-set-settings-x12.md)