---
title: "配置验证 （EDIFACT 事务集设置） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81b30a78-3a4b-4827-9b0a-af9ad3e865a3
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a9ad8f69accd0f479e05e130cc0c28fe874bb86
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-validation-edifact-transaction-set-settings"></a>配置验证（EDIFACT--事务集设置）
事务集验证设置定义了 BizTalk Server 验证从某一方收到的事务集的方式。 作为验证设置的一部分，您可以指定 BizTalk Server 将对传入交换执行哪种类型的验证  
  
> [!IMPORTANT]
>  没有属性禁用此页上，即使你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。  
  
## <a name="prerequisites"></a>先决条件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  
  
### <a name="to-configure-ack-processing-and-validation-settings"></a>配置确认处理和验证设置  
  
1.  创建 EDIFACT 编码协议中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。 若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。  
  
2.  单向协议选项卡上，在**事务设置设置**部分中，单击**验证**。  
  
3.  在网格中，您可以为不同的事务集定义不同的验证设置。 在**验证**页上，执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**Default**|选中该复选框可定义默认验证设置。|  
    |**UNH2.1**|单击此列中的空单元格，并从下拉列表中选择一个事务类型。|  
    |**Edi 类型验证**|选择**EDI 类型**来启用对交换收件人的 EDI （数据元素） 验证。 此验证可对事务集数据元素执行 EDI 验证，验证数据类型、长度限制以及空数据元素和尾部分隔符。 有关详细信息，请参阅[EDI 的类型 （数据元素） 验证](../core/edi-type-data-element-validation.md)。 **注意：**如果它在中打开的架构批注，即使没有选择此属性，将执行跨-字段/段验证。|  
    |**扩展的验证**|选择此项可让交换发件人发的扩展 (BizTalk XSD) 验证。 除了验证 XSD 数据类型之外，这还包括了对字段长度、可选性和重复计数的验证。 有关详细信息，请参阅[扩展 (BTS XSD) 验证](../core/extended-bts-xsd-validation.md)。 **注意：**可以选择此复选框才**Edi 类型验证**选择。|  
    |**允许前导和尾随零和空间**|选中则指定在 EDI 交换中的数据元素由于前导（或尾随）零或尾随空格而不符合其长度要求，但是将其删除后即符合长度要求的情况下，从参与方接收的 EDI 交换不会验证失败。 **注意：**可以选择此复选框才**Edi 类型验证**选择。|  
    |**尾随分隔符策略**|-选择**不允许**如果不想要允许尾随分隔符，在交换发件人从收到的交换中。 如果该交换包含尾部分隔符，它将被声明无效。<br />-选择**可选**接受包含或不包含尾随分隔符的交换。<br />-选择**必需**如果收到的交换必须包含尾随分隔符。|  
  
     您可以根据需要添加许多行，以定义特定交换的验证设置。  
  
     若要删除验证设置，选择行，然后单击**删除**。  
  
    > [!NOTE]
    >  在网格中编辑属性可能有些困难。 相反，你可以选择要编辑，然后编辑中的相同属性的行**编辑所选行**部分。 您在此处提供的设置将反映在所选行中。  
  
4.  单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。  
  
## <a name="see-also"></a>另请参阅  
 [配置事务集设置 (EDIFACT)](../core/configuring-transaction-set-settings-edifact.md)