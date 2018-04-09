---
title: 创建或编辑协议 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- agreements, about agreements
- agreements, modifying
- agreements, creating
- agreements
- trading partners, agreements
- creating, agreements
- modifying, agreements
- agreements, trading partners
ms.assetid: 4bbe4b57-d6ec-4448-9c80-2aecd98e0dc7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ea033770504b0e0024a831e0ad8d8727603046e
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="creating-or-editing-an-agreement"></a>创建或编辑协议
本主题介绍如何创建或编辑贸易合作伙伴协议。 贸易合作伙伴协议对贸易合作伙伴双方之间的关系做出规定，其中包括身份、合作伙伴接口流程 (PIP)、操作 URL、信号 URL、同步 URL 及相关协议。  
  
 贸易合作伙伴协议包括有关流程配置、本组织、合作伙伴及协议的设置。 所有这些设置都是协议所必需的。 您可以根据 RosettaNet PIP 或自定义架构创建流程配置，但是，您必须创建此配置。 你还必须定义本组织和伙伴组织。 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 不支持未知的参与方之间的消息交换。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 根据所有这些设置处理和验证消息。 例如，对于 CIDX 消息，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 根据 RosettaNet 实现框架 (RNIF) 版本（仅限 1.1）、0A1 协议（仅限非 0A1）和 `Is Single Action` 属性（仅限单一操作)来执行验证。 仅当设置为"1.1"，为"非 0A1"0A1 协议 RNIF 版本，将验证 CIDX 消息和`Is Single Action`属性`True`。 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 此外将验证任何协议属性是与过程配置文件设置一致。 例如，它将验证您是否已设置`Standard`"CIDX"，该配置文件的属性和协议 0A1 协议属性设置为"非 0A1"。  
  
 如果您在活动流程存在时更改协议，则可能产生无法预知的结果。 对协议属性的更改将应用，只要你单击**应用**或**确定**来接受它们，但你无法预测运行进程的哪个阶段。 更改协议后，当前流程中的任何新活动或任何新流程将使用已更改的协议属性。 但是，当您更改协议时，某个正在运行的流程可能已对正在处理的消息使用了先前的协议属性。  
  
 创建协议后，您必须将其激活，以便能够发送或接收与该协议相关联的消息。 您也可以停用协议，以防止发送或接收与协议相关联的消息。 要编辑某协议，您必须将其停用，然后在编辑后重新激活。  
  
 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将此信息保存在 BTARNCONFIG 数据库的 TPAConfig 表中。  
  
 贸易合作伙伴协议中的设置如下表所示（按选项卡排列）。默认设置是最常用的值。 创建和编辑这些设置的过程在下表之后介绍。  
  
|选项卡|设置|用法|  
|---------|-------------|-----------|  
|**常规**|**名称**|协议的唯一名称，如 Fabrikam_To_Contoso_3A2。<br /><br /> 必填字段。|  
|**常规**|**过程配置**|PIP 的标识符。<br /><br /> 此数字将标识哪一流程配置与此协议相关联。<br /><br /> 默认值为流程配置列表中的第一项。 下拉列表包括以前输入的所有流程配置。<br /><br /> 必填字段。|  
|**常规**|**我的组织**|本组织，可从下拉列表中选择。<br /><br /> 必填字段。|  
|**常规**|**伙伴组织**|合作伙伴组织，可从下拉列表中选择。<br /><br /> 必填字段。|  
|**常规**|**Description**|关于贸易合作伙伴协议的说明。|  
|**常规**|**RNIF 版本**|[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 的协议通信中将使用的 RNIF 的版本。<br /><br /> 可以是**V01.10.00**或**V02.00.01** （默认值）。<br /><br /> 必须是**V01.10.00** CIDX 有关。|  
|**常规**|**主角色**|本组织的角色。<br /><br /> 可以是发起方角色或响应方角色。|  
|**常规**|**0A1 协议**|当故障发生时，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 是否将返回失败通知消息 (0A1 PIP)。<br /><br /> 可以是**非 0A1** （默认值） 或**0A1**。<br /><br /> 必须是**非 0A1** CIDX 有关。|  
|**常规**|**用法**|指明协议将使用的方案的类型。<br /><br /> 可以是**测试**（默认值） 或**生产**。|  
|**常规**<br /><br /> (**应用程序适配器**区域)|**程序集名称**|ApplicationAdapter 的文件名，可从文件系统中选择该文件名。<br /><br /> 默认值为空字符串。|  
|**常规**<br /><br /> (**应用程序适配器区域**)|**类名**|类的名称，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]将使用从 ApplicationAdapter。<br /><br /> 默认值是\<无\>。|  
|**常规**<br /><br /> (**验证适配器区域**)|**程序集名称**|ValidationAdapter 的文件名，可从文件系统中选择该文件名。 默认值为空字符串。|  
|**常规**<br /><br /> (**验证适配器区域**)|**类名**|[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 将在 ValidationAdapter 中使用的类的名称。<br /><br /> 默认值是\<无\>。|  
|**端口**|**操作 URL**|本组织要将操作消息传送到的 URL。 例如，http://FabrikamServer/BTARNApp/RNIFReceive.aspx。<br /><br /> 如果以下全部为真，则此字段为必需字段：<br /><br /> -**是同步**过程配置设置是`False`。<br /><br /> -**是否为单一操作**过程配置设置是`True`。<br /><br /> -**主页角色**协议设置是**发起程序**。<br /><br /> 这也是必填的字段，如果满足以下条件 (在这种情况下，**信号 URL**字段也是必填):<br /><br /> -**是同步**过程配置设置是`False`。<br /><br /> -**是否为单一操作**过程配置设置是`False`。<br /><br /> -你必须在此字段中，"http://domain" 或 "https://domain" 开头的一个输入是有效的 URI。|  
|**端口**|**信号 URL**|本组织要将信号消息传送到的 URL。 例如，http://FabrikamServer/BTARNApp/RNIFReceive.aspx。<br /><br /> 如果以下为真，则此字段为必需字段：<br /><br /> -**是同步**过程配置设置是`False`。<br /><br /> -**是否为单一操作**过程配置设置是`True`。<br /><br /> -**主页角色**协议设置是**响应方**。<br /><br /> 这也是必填的字段，如果满足以下条件 (在这种情况下，**操作 URL**字段也是必填):<br /><br /> -**是同步**过程配置设置是`False`。<br /><br /> -**是否为单一操作**过程配置设置是`False`。<br /><br /> 您必须在此字段中输入以 “http://domain” 或 “https://domain” 开头的有效 URI。|  
|**端口**|**同步 URL**|本组织通过 HTTP 适配器建立连接时所使用的 URL。 例如，http://FabrikamServer/BTARNApp/RNIFReceive.aspx。<br /><br /> 如果以下为真，则此字段为必需字段：<br /><br /> -**是同步**过程配置设置是`True`。<br /><br /> -**主页角色**协议设置是**发起程序**。<br /><br /> 您必须在此字段中输入以 “http://domain” 或 “https://domain” 开头的有效 URI。|  
|**协议**|**Digest 方法**|用于计算传入消息摘要的协议，以确保不可否认性。<br /><br /> **从开始[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]和更高版本**，SHA2 支持将自动包含。 选项包括： **MD5**， **sha-1**， **SHA 256** （默认值）、 **sha-384**，和**sha-512**。<br /><br />有关以前[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]版本中，选项包括**MD5**或**sha-1** （默认值）。<br /><br /> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]接收管道接收并对消息进行解密，即使使用的协议对邮件进行加密和**编码**协议中的此选项卡上的设置不匹配。 因此，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]接收消息以 RC2 40 或 3DES 进行加密。<br /><br /> 所有传出签名的消息具有 sha-1 的摘要。|  
|**协议**|**将所有部分都编码**|系统是否对多部分消息的所有部分进行集中编码。<br /><br /> 可以是`True`或`False`（默认值）。<br /><br /> 当`True`，将使用由指示的方法编码多部分消息的所有部分`Encoding`属性。<br /><br /> 当`False`，系统将仅编码使用由指示的方法的附件`Encoding`属性。 (始终编码附件时所使用的方法由发送管道`Encoding`属性。)默认情况下，当将此属性设置为`False`，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]的 quoted printable 格式进行编码消息 （RNIF 2.01，RNIF 1.1 中的三个部分中的四个部分） 的其他部分。|  
|**协议**|**编码**|用于将所有部分都编码的协议 (如果**将所有部分都都编码**框是`True`) 或附件 (如果**将所有部分都都都编码**框是`False`)。<br /><br /> 可以是**8 位**， **base 64** （默认值），或**quoted printable**。|  
|**协议**|**加密算法**|用于对传入或传出消息进行加密的算法。<br /><br /> **从开始[!INCLUDE[bts2016_md](../../includes/bts2016-md.md)]和更高版本**，AES 支持将自动包含。 选项包括**RC2 40**， **3DES**， **AES128** （默认值）、 **AES192**，和**AES256**。 <br /><br />有关以前[!INCLUDE[btsBizTalkServerNoVersion_md](../../includes/btsbiztalkservernoversion-md.md)]版本中，选项包括**RC2 40** （默认值） 或**3DES**。<br /><br /> 加密算法才能起作用，如果设置了`Is Persistent Confidentiality Required`属性为**负载**或**负载容器**相应的过程配置中。|  
|**协议**|**加密方向**|系统将加密传入消息或传出消息，或者对二者都加密。<br /><br /> 可以是**入站**，**出站**，或**入站/出站**（默认值）。<br /><br /> 加密方向设置才能起作用，如果设置了`Is Persistent Confidentiality Required`属性为**负载**或**负载容器**相应的过程配置中。|  
|**自定义属性**|**名称**|自定义属性的名称。<br /><br /> 您可以为每份协议设置自定义属性。 如果您新建了自定义专用流程，那么您可以在处理不同协议时使用这些自定义属性。<br /><br /> 您可以使用 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK 中的 `RuntimeConfig.GetTPACustomConfigValue` 方法，以便从 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 配置中检索自定义属性。<br /><br /> `Name`属性必须是唯一的且不为空。<br /><br /> 您可以输入以下自定义值：<br /><br /> - **AAR**。 这是“要求接受确认”自定义属性。 此属性仅适用于 RNIF 1.1。 将其设置为**false** （这是不区分大小写） 需要仅接收确认，不接受确认。 如果**AAR**设置为任何非**false**、 然后响应方公共过程必须发送验收确认，和发起程序公共过程应接受确认。 如果将“AAR”设置为“false”，则确认收到后公用流程即完成。<br /><br /> - **HPCC**. 这是本组织合作伙伴分类代码。 此属性仅适用于 RNIF 1.1。 使用此属性可以在传出消息的服务头中将本组织合作伙伴的 GlobalPartnerClassificationCode 元素设置为“值”列中的条目。 此值将覆盖本组织配置中的本组织分类属性。 当本组织可以具有多个分类时，可使用此自定义属性。<br /><br /> - **PPCC**. 这是合作伙伴配置文件分类代码。 此属性仅适用于 RNIF 1.1。 使用此属性可以在传出消息的服务头中将合作伙伴的 GlobalPartnerClassificationCode 元素设置为“值”列中的条目。 此值将覆盖合作伙伴配置中的合作伙伴分类属性。 当合作伙伴可以具有多个分类时，可使用此自定义属性。|  
|**自定义属性**|**Value**|自定义属性的值。|  
  
### <a name="to-create-a-trading-partner-agreement"></a>创建贸易合作伙伴协议  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**.  
  
2.  在 BTARN 管理控制台中，展开 [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]。  
  
3.  右键单击**协议**，指向**新建**，然后单击**协议**。  
  
4.  在新的协议属性对话框中，在**常规**，**端口**，**协议**，和**自定义属性**选项卡上，输入值有关设置。 有关这些设置的信息，请参阅上表。  
  
5.  单击 **“确定”**。  
  
    > [!NOTE]
    >  只有激活协议之后，BTARN 才接受与该协议有关的消息。  
  
6.  右键单击在右窗格中，协议的名称，然后单击**激活**。  
  
> [!NOTE]
>  如果你已经激活协议，你可以右键单击在右窗格中，协议的名称，然后单击**停用**以防止与从正在发送或接收协议关联的任何消息。  
  
### <a name="to-edit-a-trading-partner-agreement"></a>编辑贸易合作伙伴协议  
  
1.  单击**启动**，指向**所有程序**，指向**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**.  
  
2.  在 BTARN 管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击**协议**节点。  
  
3.  右键单击你想要编辑，然后单击协议**属性**。  
  
4.  在**\<***协议名称***\>**属性对话框中，在**常规**和**联系人属性**选项卡上，根据需要更改设置。 有关这些设置的信息，请参阅上表。  
  
5.  单击 **“确定”**。  
  
## <a name="see-also"></a>另请参阅  
 [管理配置、 证书、 数据库和安全](manage-configuration-certificates-databases-security.md)   
 [管理 BTARN 配置](../../adapters-and-accelerators/accelerator-rosettanet/administering-the-btarn-configuration.md)