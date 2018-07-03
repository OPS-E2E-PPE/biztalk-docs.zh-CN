---
title: 配置业务配置文件属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.admin.businessprofile.properties
ms.assetid: d3c87777-9bcd-4482-bbb7-efea08cdeead
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e398c943a2bb6fdb119b671e1593eae71d93a6be
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019249"
---
# <a name="configuring-business-profile-properties"></a>配置业务配置文件属性
一个业务配置文件代表组织中的一个业务部门。 就像一个组织可以有多个部门（会计、采购、发货等等）一样，一个参与方也可有许多业务配置文件，每个业务配置文件代表组织中一个业务部门。 业务配置文件属性包含下列信息：  

- 常规信息，例如业务配置文件名称  

- 可以与业务配置文件相关联的唯一标识  

- 编码设置（针对 X12 和 EDIFACT 消息）和定义业务配置文件该如何从其他参与方发送或接收消息的协议设置 (AS2)。  

  有关业务配置文件的详细信息，请参阅[业务配置文件](http://msdn.microsoft.com/library/f8286130-57fe-40ed-9fd8-81da2c8baaaf)。 有关编码和传输协议设置的详细信息，请参阅[协议设置](../core/protocol-settings.md)。  

## <a name="prerequisites"></a>必要條件  
 必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。  

### <a name="to-configure-business-profile-properties"></a>配置业务配置文件属性  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点。 在中**参与方和业务配置文件**窗格中，右键单击参与方，新的、 指向添加，然后单击**业务配置文件**。  

2. 在中**常规**选项卡中，**常规**页上，执行以下操作：  


   |                 使用此选项                 |                                                                                                                       执行的操作                                                                                                                       |
   |------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                 **名称**                 |                                                                                                             输入业务配置文件名称。                                                                                                             |
   |             **Description**              |                                                                                                     为该业务配置文件输入说明。                                                                                                      |
   | **其他属性 – 名称/值** | 输入一个名称/值对以存储有关参与方的任何信息。 可以根据需要添加任意数量的名称/值对。 **注意：** 名称 / 值对不能由 BizTalk Server 进行任何处理; 此数据是为了仅提供信息。 |
   |                **删除**                |                                                                                                     单击此项可删除所选的名称/值对。                                                                                                      |


3. 如果需要，则为该业务配置文件添加业务标识。 在中**常规**选项卡中，**标识**页上，执行以下操作：  

   > [!NOTE]
   >  在此阶段中添加业务标识不是强制性的。 您也可以在以后将业务标识作为业务配置文件的协议的一部分进行添加。 如果您选择现在添加业务标识，它们在为此业务配置文件创建协议时即可用。  

   |   使用此选项    |                                                                                                                                                                                                                                                                      执行的操作                                                                                                                                                                                                                                                                       |
   |---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   **名称**    |                                                                                        单击空单元格，从下拉网格中选择一个为组织提供唯一业务标识的认证机构。 例如， **D-U-N-S (Dun & Bradstreet)**。 两个业务合作伙伴可以选择一个双方商定的业务标识。 对于这种情况下，选择**双方**（适用于 EDIFACT) 或**双方 (X12)** （适用于 X12)。                                                                                         |
   | **Qualifier** |                                                                                                                                                                                                                                       显示基于为选定的值的预定义的值**名称**。                                                                                                                                                                                                                                       |
   |   **ReplTest1**   | 输入业务标识的值。 在提供业务标识的值时，您必须注意以下事项。<br /><br /> -对于给定参与方，您可以使用相同的标识名称和标识值组合的多个业务配置文件。 例如，可以有两个业务配置文件与参与方**名称**作为**双方 (X12)** 并**值**作为**THEM**。<br />-多个参与方，不能具有使用相同的标识名称和标识值组合的两个业务配置文件。 |
   |  **删除**   |                                                                                                                                                                                                                                                        单击此项可删除所选标识。                                                                                                                                                                                                                                                         |


4. 如果需要，为 X12 编码的消息添加协议设置。  

   1.  在中**配置文件属性**对话框中，从右上角，单击**添加协议设置**，指向**编码设置**，然后单击**X12**.  

   2.  获取旁边添加一个新选项卡**常规**选项卡。上**常见**的新添加的页选项卡上，在**协议设置名称**文字框中，输入一个名称以标识此组的编码协议设置。 该选项卡的名称也将设置为您在此文本框中指定的值。  

   3.  您可以定义 X12 属性作为业务配置文件的一部分，或直接在协议中定义。 如果定义这些属性作为业务配置文件的一部分，则在创建协议时将有相同的可用设置。 因为相同的属性可以在两个位置进行设置，此文档提供有关如何将属性仅设置为协议一部分的说明。 如果您要将属性设置为业务配置文件的一部分，下表提供了包含属性设置信息的相关部分的链接。  

       > [!NOTE]
       >  入站设置将应用到参与方收到的所有消息。 出站设置将应用到参与方发送的所有消息。  

       > [!NOTE]
       >  即使您指定了协议设置作为业务配置文件的一部分，也始终可以覆盖特定协议的这些设置。  

       |设置|描述位置|  
       |-------------|------------------------------|  
       |**入站设置 > 交换设置 > 验证**|[配置验证（X12-交换设置）](../core/configuring-validation-x12-interchange-settings.md)|  
       |**入站设置 > 交换设置 > 本地主机设置**|[配置本地主机设置 （X12-交换设置）](../core/configuring-local-host-settings-x12-interchange-settings.md) （接收方设置）|  
       |**入站设置 > 事务集设置 > 事务集列表**|[配置事务集列表 (X12)](../core/configuring-transaction-set-list-x12.md)|  
       |**入站设置 > 事务集设置 > 验证**|[配置验证（X12-事务集设置）](../core/configuring-validation-x12-transaction-set-settings.md)|  
       |**入站设置 > 事务集设置 > 本地主机设置**|[配置本地主机设置（X12-事务集设置）](../core/configuring-local-host-settings-x12-transaction-set-settings.md)|  
       |**出站设置 > 交换设置 > 其他标识符**|[配置标识符 (X12)](../core/configuring-identifiers-x12.md)|  
       |**出站设置 > 交换设置 > 确认**|[配置确认 (X12)](../core/configuring-acknowledgements-x12.md)|  
       |**出站设置 > 交换设置 > 信封**|[配置信封（X12-交换设置）](../core/configuring-envelopes-x12-interchange-settings.md)|  
       |**出站设置 > 交换设置 > 字符集和分隔符**|[配置字符集和分隔符 (X12)](../core/configuring-charset-and-separators-x12.md)|  
       |**出站设置 > 交换设置 > 的控制编号**|[配置本地主机设置 （X12-交换设置）](../core/configuring-local-host-settings-x12-interchange-settings.md) （发件人的设置）|  
       |**出站设置 > 事务集设置 > 信封**|[配置信封（X12-事务集设置）](../core/configuring-envelopes-x12-transaction-set-settings.md)|  

       > [!NOTE]
       >  您可以有多个为业务配置文件定义的 X12 编码协议设置。  

5. 如果需要，则为 EDIFACT 编码的消息添加协议设置。  

   1.  在中**配置文件属性**对话框中，从右上角，单击**添加协议设置**，指向**编码设置**，然后单击**EDIFACT**。  

   2.  获取旁边添加一个新选项卡**常规**选项卡。上**常见**的新添加的页选项卡上，在**协议设置名称**文字框中，输入一个名称以标识此组的编码协议设置。 该选项卡的名称也将设置为您在此文本框中指定的值。  

   3.  您可以定义 EDIFACT 属性作为业务配置文件的一部分，或直接在协议中定义。 如果定义这些属性作为业务配置文件的一部分，则在创建协议时将有相同的可用设置。 因为相同的属性可以在两个位置进行设置，此文档提供有关如何将属性仅设置为协议一部分的说明。 如果您要将属性设置为业务配置文件的一部分，下表提供了包含属性设置信息的相关部分的链接。  

       > [!NOTE]
       >  入站设置将应用到参与方收到的所有消息。 出站设置将应用到参与方发送的所有消息。  

       > [!NOTE]
       >  即使您指定了协议设置作为业务配置文件的一部分，也始终可以覆盖特定协议的这些设置。  

       |设置|描述位置|  
       |-------------|------------------------------|  
       |**入站设置 > 交换设置 > 其他标识符**|[配置标识符 (EDIFACT)](../core/configuring-identifiers-edifact.md)|  
       |**入站设置 > 交换设置 > 验证**|[配置验证（EDIFACT-交换设置）](../core/configuring-validation-edifact-interchange-settings.md)|  
       |**入站设置 > 交换设置 > 本地主机设置**|[配置本地主机设置 （EDIFACT-交换设置）](../core/configuring-local-host-settings-edifact-interchange-settings.md) （接收方设置）|  
       |**入站设置 > 事务集设置 > 事务集列表**|[配置事务集列表 (EDIFACT)](../core/configuring-transaction-set-list-edifact.md)|  
       |**入站设置 > 事务集设置 > 验证**|[配置验证（EDIFACT-事务集设置）](../core/configuring-validation-edifact-transaction-set-settings.md)|  
       |**入站设置 > 事务集设置 > 本地主机设置**|[配置本地主机设置（EDIFACT-事务集设置）](../core/configuring-local-host-settings-edifact-transaction-set-settings.md)|  
       |**出站设置 > 交换设置 > 其他标识符**|[配置标识符 (EDIFACT)](../core/configuring-identifiers-edifact.md)|  
       |**出站设置 > 交换设置 > 确认**|[配置确认 (EDIFACT)](../core/configuring-acknowledgements-edifact.md)|  
       |**出站设置 > 交换设置 > 信封**|[配置信封（EDIFACT-交换设置）](../core/configuring-envelopes-edifact-interchange-settings.md)|  
       |**出站设置 > 交换设置 > 字符集和分隔符**|[配置字符集和分隔符 (EDIFACT)](../core/configuring-charset-and-separators-edifact.md)|  
       |**出站设置 > 交换设置 > 的控制编号**|[配置本地主机设置 （EDIFACT-交换设置）](../core/configuring-local-host-settings-edifact-interchange-settings.md) （发件人的设置）|  
       |**出站设置 > 事务集设置 > 信封**|[配置信封（EDIFACT-事务集设置）](../core/configuring-envelopes-edifact-transaction-set-settings.md)|  

       > [!NOTE]
       >  您可以有多个为业务配置文件定义的 EDIFACT 编码协议设置。  

6. 如果需要，则为 AS2 传输添加协议设置。  

   1.  在中**配置文件属性**对话框中，从右上角，单击**添加协议设置**，指向**传输设置**，然后单击**AS2**.  

   2.  获取旁边添加一个新选项卡**常规**选项卡。上**常见**的新添加的页选项卡上，在**协议设置名称**文字框中，输入一个名称以标识此组的传输协议设置。 该选项卡的名称也将设置为您在此文本框中指定的值。  

   3.  您可以定义 AS2 属性作为业务配置文件的一部分，或直接在协议中定义。 如果定义这些属性作为业务配置文件的一部分，则在创建协议时将有相同的可用设置。 因为相同的属性可以在两个位置进行设置，此文档提供有关如何将属性仅设置为协议一部分的说明。 如果您要将属性设置为业务配置文件的一部分，下表提供了包含属性设置信息的相关部分的链接。  

       > [!NOTE]
       >  入站设置将应用到参与方收到的所有消息。 出站设置将应用到参与方发送的所有消息。  

       > [!NOTE]
       >  即使您指定了协议设置作为业务配置文件的一部分，也始终可以覆盖特定协议的这些设置。  

       |设置|描述位置|  
       |-------------|------------------------------|  
       |**入站设置 > 验证**|[配置验证（AS2）](../core/configuring-validation-as2.md)|  
       |**入站设置 > 本地主机设置 > 消息的 HTTP 设置**|[配置消息的 HTTP 设置](../core/configuring-http-settings-for-messages.md)|  
       |**入站设置 > 本地主机设置 > 生成 MDN 设置**|[配置接收器 MDN 设置](../core/configuring-receiver-mdn-settings.md)|  
       |**入站设置 > 本地主机设置 > 消息跟踪 (NRR)**|[配置接收方消息跟踪 (NRR)](../core/configuring-receiver-message-tracking-nrr.md)|  
       |**出站设置 > 确认 (Mdn)**|[配置确认 (MDN) (AS2)](../core/configuring-acknowledgements-mdns-as2.md)|  
       |**出站设置 > 本地主机设置 > 常规**|[配置常规本地主机设置 (AS2)](../core/configuring-general-local-host-settings-as2.md)|  
       |**出站设置 > 本地主机设置 > MDN 的 HTTP 设置**|[配置 MDN 的 HTTP 设置](../core/configuring-http-settings-for-mdns.md)|  
       |**出站设置 > 本地主机设置 > 消息跟踪 (NRR)**|[配置发送方消息跟踪 (NRR)](../core/configuring-sender-message-tracking-nrr.md)|  
       |**出站设置 > 签名证书**|[配置签名证书 (AS2)](../core/configuring-signature-certificates-as2.md)|  

       > [!NOTE]
       >  您可以有多个为业务配置文件定义的 AS2 传输协议设置。  

7. 单击**Apply**以接受这些属性，或单击**确定**即可完成配置设置。 以上任一操作均将验证设置。  

## <a name="see-also"></a>请参阅  
 [配置 EDI 属性](../core/configuring-edi-properties.md)