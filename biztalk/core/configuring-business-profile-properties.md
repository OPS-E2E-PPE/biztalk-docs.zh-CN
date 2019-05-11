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
ms.openlocfilehash: 6cb1805b67a541df7cfa227a14697eb327b6e4ca
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356197"
---
# <a name="configuring-business-profile-properties"></a>配置业务配置文件属性
业务配置文件表示的组织中一个业务部门。 就像一个组织可以有多个部门 （会计、 采购、 发货等），一个参与方可以有多个业务配置文件，每个资源表示一个业务部门的组织中。 业务配置文件属性包含下列信息：  

- 常规信息，如业务配置文件名称  

- 可以与业务配置文件相关联的唯一标识  

- 编码 （X12 和 EDIFACT 消息） 的设置和协议设置 (AS2)，用于定义如何发送或接收来自另一方的消息的业务配置文件。  

  有关业务配置文件的详细信息，请参阅[业务配置文件](http://msdn.microsoft.com/library/f8286130-57fe-40ed-9fd8-81da2c8baaaf)。 有关编码和传输协议设置的详细信息，请参阅[协议设置](../core/protocol-settings.md)。  

## <a name="prerequisites"></a>先决条件  
 必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。  

### <a name="to-configure-business-profile-properties"></a>若要配置业务配置文件属性  

1. 在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，单击**方**节点。 在中**参与方和业务配置文件**窗格中，右键单击参与方，新的、 指向添加，然后单击**业务配置文件**。  

2. 在中**常规**选项卡中，**常规**页上，执行以下操作：  


   |                 使用此选项                 |                                                                                                                       执行的操作                                                                                                                       |
   |------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                 **名称**                 |                                                                                                             输入业务配置文件名称。                                                                                                             |
   |             **说明**              |                                                                                                     输入业务配置文件的说明。                                                                                                      |
   | **其他属性 – 名称/值** | 输入的名称-值对来存储有关参与方的任何信息。 您可以添加所需的任意多个名称 / 值对。 **注意：** 名称 / 值对不进行任何处理; 使用由 BizTalk Server此数据是为了仅提供信息。 |
   |                **删除**                |                                                                                                     单击此项可删除所选的名称-值对。                                                                                                      |


3. 如果需要，添加业务标识的业务配置文件。 在中**常规**选项卡中，**标识**页上，执行以下操作：  

   > [!NOTE]
   >  在此阶段中添加业务标识不是必需的。 作为业务配置文件的协议的一部分，可以添加业务标识也更高版本。 如果您选择添加业务标识现在，他们可创建此业务配置文件的协议时。  

   |   使用此选项    |                                                                                                                                                                                                                                                                      执行的操作                                                                                                                                                                                                                                                                       |
   |---------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |   **名称**    |                                                                                        单击空单元格，并从下拉列表网格中，选择提供唯一业务标识到组织的认证机构。 例如， **D-U-N-S (Dun & Bradstreet)**。 两个业务合作伙伴可以选择相互议定的业务标识。 对于这种情况下，选择**双方**（适用于 EDIFACT) 或**双方 (X12)** （适用于 X12)。                                                                                         |
   | **Qualifier** |                                                                                                                                                                                                                                       显示基于为选定的值的预定义的值**名称**。                                                                                                                                                                                                                                       |
   |   **ReplTest1**   | 输入业务标识的值。 提供的业务标识时，必须考虑以下注意事项。<br /><br /> -对于给定参与方，您可以使用相同的标识名称和标识值组合的多个业务配置文件。 例如，可以有两个业务配置文件与参与方**名称**作为**双方 (X12)** 并**值**作为**THEM**。<br />-多个参与方，不能具有使用相同的标识名称和标识值组合的两个业务配置文件。 |
   |  **删除**   |                                                                                                                                                                                                                                                        单击此项可删除所选的标识。                                                                                                                                                                                                                                                         |


4. 如果需要，添加 X12 编码消息的协议的设置。  

   1.  在中**配置文件属性**对话框中，从右上角，单击**添加协议设置**，指向**编码设置**，然后单击**X12**.  

   2.  获取旁边添加一个新选项卡**常规**选项卡。上**常见**的新添加的页选项卡上，在**协议设置名称**文字框中，输入一个名称以标识此组的编码协议设置。 选项卡的名称也设置为在文本框中指定的值。  

   3.  您可以定义 X12 属性作为业务配置文件或直接在协议中的一部分。 如果定义属性作为业务配置文件的一部分，创建协议时将可供你相同的设置。 可以在两个位置设置相同的属性，因为本文档将说明了如何将属性设置仅为协议的一部分。 如果你想要将属性设置为业务配置文件的一部分下, 表提供了指向包含有关设置属性的信息的相关部分。  

       > [!NOTE]
       >  入站的设置适用于所有参与方接收的消息。 出站设置将应用于所有参与方发送的消息。  

       > [!NOTE]
       >  即使您指定的协议设置作为业务配置文件的一部分，可以始终覆盖特定协议的设置。  

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
       >  可以有多个 X12 编码协议设置定义为业务配置文件。  

5. 如果需要，添加 EDIFACT 编码消息的协议的设置。  

   1.  在中**配置文件属性**对话框中，从右上角，单击**添加协议设置**，指向**编码设置**，然后单击**EDIFACT**。  

   2.  获取旁边添加一个新选项卡**常规**选项卡。上**常见**的新添加的页选项卡上，在**协议设置名称**文字框中，输入一个名称以标识此组的编码协议设置。 选项卡的名称也设置为在文本框中指定的值。  

   3.  可以作为一部分的业务配置文件或直接在协议中定义的 EDIFACT 属性。 如果定义属性作为业务配置文件的一部分，创建协议时将可供你相同的设置。 可以在两个位置设置相同的属性，因为本文档将说明了如何将属性设置仅为协议的一部分。 如果你想要将属性设置为业务配置文件的一部分下, 表提供了指向包含有关设置属性的信息的相关部分。  

       > [!NOTE]
       >  入站的设置适用于所有参与方接收的消息。 出站设置将应用于所有参与方发送的消息。  

       > [!NOTE]
       >  即使您指定的协议设置作为业务配置文件的一部分，可以始终覆盖特定协议的设置。  

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
       >  您可以具有多个业务配置文件定义 EDIFACT 编码协议设置。  

6. 如果需要，添加 AS2 传输协议设置。  

   1.  在中**配置文件属性**对话框中，从右上角，单击**添加协议设置**，指向**传输设置**，然后单击**AS2**.  

   2.  获取旁边添加一个新选项卡**常规**选项卡。上**常见**的新添加的页选项卡上，在**协议设置名称**文字框中，输入一个名称以标识此组的传输协议设置。 选项卡的名称也设置为在文本框中指定的值。  

   3.  可以作为一部分的业务配置文件或直接在协议中定义的 AS2 属性。 如果定义属性作为业务配置文件的一部分，创建协议时将可供你相同的设置。 可以在两个位置设置相同的属性，因为本文档将说明了如何将属性设置仅为协议的一部分。 如果你想要将属性设置为业务配置文件的一部分下, 表提供了指向包含有关设置属性的信息的相关部分。  

       > [!NOTE]
       >  入站的设置适用于所有参与方接收的消息。 出站设置将应用于所有参与方发送的消息。  

       > [!NOTE]
       >  即使您指定的协议设置作为业务配置文件的一部分，可以始终覆盖特定协议的设置。  

       |设置|描述位置|  
       |-------------|------------------------------|  
       |**入站设置 > 验证**|[配置验证 (AS2)](../core/configuring-validation-as2.md)|  
       |**入站设置 > 本地主机设置 > 消息的 HTTP 设置**|[配置消息的 HTTP 设置](../core/configuring-http-settings-for-messages.md)|  
       |**入站设置 > 本地主机设置 > 生成 MDN 设置**|[配置接收器 MDN 设置](../core/configuring-receiver-mdn-settings.md)|  
       |**入站设置 > 本地主机设置 > 消息跟踪 (NRR)**|[配置接收方消息跟踪 (NRR)](../core/configuring-receiver-message-tracking-nrr.md)|  
       |**出站设置 > 确认 (Mdn)**|[配置确认 (Mdn) (AS2)](../core/configuring-acknowledgements-mdns-as2.md)|  
       |**出站设置 > 本地主机设置 > 常规**|[配置常规本地主机设置 (AS2)](../core/configuring-general-local-host-settings-as2.md)|  
       |**出站设置 > 本地主机设置 > MDN 的 HTTP 设置**|[配置 MDN 的 HTTP 设置](../core/configuring-http-settings-for-mdns.md)|  
       |**出站设置 > 本地主机设置 > 消息跟踪 (NRR)**|[配置发送方消息跟踪 (NRR)](../core/configuring-sender-message-tracking-nrr.md)|  
       |**出站设置 > 签名证书**|[配置签名证书 (AS2)](../core/configuring-signature-certificates-as2.md)|  

       > [!NOTE]
       >  可以有多个 AS2 传输协议设置定义为业务配置文件。  

7. 单击**Apply**以接受这些属性，或单击**确定**即可完成配置设置。 以上任一操作将验证设置。  

## <a name="see-also"></a>请参阅  
 [配置 EDI 属性](../core/configuring-edi-properties.md)