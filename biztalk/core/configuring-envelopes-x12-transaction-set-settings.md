---
title: 配置信封 （X12 事务集设置） |Microsoft 文档
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
ms.openlocfilehash: 519062fa4647cdc2c7c39dda19373ff888eaf601
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234333"
---
# <a name="configuring-envelopes-x12-transaction-set-settings"></a>配置信封（X12--事务集设置）
在**Envelops**页**事务设置设置**部分中，你定义 BizTalk Server 如何生成它将发送到方的 X12 编码交换的 GS 和 ST 段。 GS 段为 X12 编码的交换标识和指定功能组。 ST 段是 X12 编码的交换的消息标头。  
  
 在此页上，你将相关联的值**GS1**， **GS2**， **GS3**， **GS4**， **GS5**， **GS7**，和**GS8**具有的值的数据元素**事务类型**，**版本/发行版**，和**目标命名空间**数据元素。 BizTalk 确定 BizTalk XML 消息已设置的值**事务类型**，**版本/发行版**，和**目标命名空间**的网格中，行中的元素BizTalk 将填充**GS1**， **GS2**， **GS3**， **GS4**， **GS5**， **GS7**，和**GS8**同一行的网格中的值交换的信封中的传出数据元素。 值**事务类型**，**版本/发行版**，和**目标命名空间**元素必须是唯一的。  
  
> [!NOTE]
>  如果为网格中的任意字段输入设置，然后删除该设置，则必须删除整行，否则对该页的验证将失败。  
  
> [!NOTE]
>  本主题还适用于与 HIPAA 相关的设置。  
  
> [!IMPORTANT]
>  所有属性上将都禁用**A 方-> 方 B**单向协议选项卡，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**检查框 a 方。但是，在中相同页面上启用的所有属性**B 方-> A 方**选项卡上，如果创建 a 方。 时选中复选框  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-define-the-gs-and-st-segments"></a>若要定义 GS 和 ST 段  
  
1.  创建 X12 编码协议中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。 若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**事务设置设置**部分中，单击**包络线**。  
  
3.  在网格的某行中，输入以下内容：  
  
    -   有关**事务类型**字段中，为事务集标识符代码，从下拉列表中选择一个值。  
  
    -   有关**版本/发行版**，输入一个字母数字值，该值最少包含一个字符，最多 12 个字符。  
  
    -   有关**目标命名空间**元素，从下拉列表中，选择一个值，或输入命名空间。  
  
        > [!NOTE]
        >  BizTalk Server 会将这些值与它所生成的交换的关联值进行比较。  
  
4.  在同一行网格中，输入以下内容：  
  
    -   有关**GS1**，从下拉列表中选择的功能的代码的值。 此字段为可选字段。  
  
    -   有关**GS2**，不少于两个字符，最多包含 15 个字符的该应用程序发件人输入一个字母数字值。 这是必填字段。  
  
    -   有关**GS3**，为两个字符的最小值和最多 15 个字符的应用程序收件人输入一个字母数字值。 这是必填字段。  
  
    -   有关**GS4**，选择**CCYYMMDD**或**YYMMDD**。 此字段为可选字段  
  
    -   有关**GS5**，选择**HHMM**， **HHMMSS**，或**HHMMSSdd**。 此字段为可选字段  
  
    -   有关**GS7**，从下拉列表中选择一个值为责任代理。 此字段为可选字段。  
  
    -   有关**GS8**，为标识最少包含一个字符，最多 12 个字符的文档输入一个字母数字值。 此字段为可选字段。  
  
        > [!NOTE]
        >  这些将是 BizTalk Server 将生成如果该交换的 GS 字段中输入的值**事务类型**，**版本/发行版**，和**目标命名空间**同一行中的元素是交换关联的匹配项。  
  
5.  要在网格中输入其他行，请重复步骤 3 和步骤 4。  
  
6.  对于在网格中的一个行，请单击**默认**以将其指定为默认行。  
  
    > [!NOTE]
    >  如果消息没有包含的匹配项**事务类型**，**版本/发行版**，和**目标命名空间**任何行，BizTalk Server 中的元素将填充消息值**GS1**， **GS2**， **GS3**， **GS5**， **GS7**，和**GS8**默认行中的元素。 将使用这些值，即使消息不具有与匹配**事务类型**，**版本/发行版**，和**目标命名空间**默认行的元素。  
  
    > [!NOTE]
    >  如果没有默认值是不匹配的已选定、 传入文档**事务类型**，**版本/发行版**，和**目标命名空间**的任何行的元素将被挂起.  
  
7.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置事务集设置 (X12)](../core/configuring-transaction-set-settings-x12.md)