---
title: 环回 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- agreements, 0A1 agreements
- loopbacks, running
- loopbacks, 0A1 agreements
- loopbacks, about loopbacks
- loopbacks, 0A1 messages
- agreements, loopback agreements
- messages, 0A1 messages
- loopbacks
- Loopback utility
- loopbacks, syntax
- 0A1 messages
- loopbacks, Loopback utility
- syntax [loopbacks]
- agreements, Loopback utility
ms.assetid: b4ebbdac-05be-4dfc-a133-6b752994e85a
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4fcd620ff90a4ca1650e4a93ad05194c1749774
ms.sourcegitcommit: 436ebffd959a9c4bdaafd4da9a5843c59a018eb7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2018
ms.locfileid: "34855648"
---
# <a name="loopback"></a>环回
使用 Loopback 实用工具可以自动生成环回协议，它是本组织到合作伙伴协议的镜像副本。 这使你能够在单个计算机上执行本组织到合作伙伴以及合作伙伴到本组织的消息交换。 此实用工具可以用于带有 0A1 消息的方案，也可以用于不带 0A1 消息的方案。 你可以为操作-消息（非 0A1）协议或 0A1 协议创建环回协议。  
  
 使用该实用工具还可以登记或取消登记发件人角色的本组织。 当你使用该实用程序启用本组织时，它将创建两个发送端口，\<主\>。异步和\<主页\>。同步的组织使用其合作伙伴与进行通信。  
  
## <a name="location-in-sdk"></a>在 SDK 中的位置  
 \<*驱动器*\>\ Program Files (x86) \Microsoft BizTalk\<版本\>RosettaNet\SDK\ 快捷键  
  
## <a name="running-loopback"></a>运行环回  
  
#### <a name="to-run-loopback"></a>运行 Loopback  
  
1.  打开命令提示符。  
  
2.  将移动到\<*驱动器*\>\ Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\\。  
  
3.  在命令提示符处，键入**环回**，键入必选和相应的交换机，然后按 enter 键。  
  
## <a name="syntax-for-loopback"></a>Loopback 的语法  
 下面给出了用于启动此命令行实用工具的语法：  
  
```  
Loopback [/enable|/disable <home_organization>] [/mirror|/unmirror <agreement_name>] [/NoF <0A1_agreement>]  
```  
  
## <a name="syntax-description"></a>语法说明  
 下表描述了 Loopback 实用工具使用的语法的各个部分。  
  
|**语法**|**Description**|  
|----------------|---------------------|  
|**enable**|登记组织 < home_organization > 中指定的发件人角色。 它将创建两个发送端口，\<主页\>。异步和\<主页\>。同步伙伴用来返回到本组织进行通信。|  
|**disable**|取消登记发件人角色的本组织。|  
|**home_organization**|要登记或取消登记的发件人角色的合作伙伴。|  
|**mirror**|创建基于协议中指定的环回协议\< **agreement_name**\>。|  
|**unmirror**|删除基于协议中指定的环回协议\< **agreement_name\>**。|  
|**agreement_name**|在环回方案中要镜像或取消镜像的协议。|  
|**起**|集**0A1 协议**镜像到环回实用程序的操作消息协议属性\<0A1_agreement\>。 A **/NoF**交换机可以仅添加到环回命令还包含 **/镜像**切换。|  
|**0A1_agreement**|agreement_name 的镜像协议使用的 0A1 协议。 此协议是通过镜像响应方 0A1 协议而生成的。|  
  
## <a name="remarks"></a>Remarks  
 Loopback 实用工具在创建环回协议时切换角色。 如果某组织在原始协议中是本组织，则该实用工具会使其成为环回协议中的合作伙伴组织。 同样，如果某组织在原始协议中是合作伙伴组织，则该实用工具会使其成为环回协议中的本组织。 该实用工具还会切换本组织角色的属性设置。 如果在原始协议中本组织角色属性是发起方，则该实用工具会将其更改为响应方，反之亦然。 而所有其他属性保持不变。  
  
 Loopback 实用工具将环回协议的名称命名为与原始协议相同，只是在前面加上“loopback:”。 为避免混淆，请不要将协议命名为以“loopback”开头。  
  
 如果针对已经生成环回协议的协议运行该实用工具，则该实用工具将取消镜像现有的环回协议，然后创建新的环回协议。  
  
 由于在 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理控制台中无法创建镜像协议，所以需要使用 Loopback 实用工具。 无法创建在协议[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台对其进行了互换本组织伙伴组织中，主角色属性和所有其他字段均与现有协议的字段相同。 同样，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不支持更改直接在控制台中的环回协议。 如果尝试在控制台中打开环回协议，你将收到一条错误消息。 如果必须更改环回协议，请先更改起始协议，然后对该协议再次运行 Loopback 实用工具，以重新生成该环回协议。  
  
> [!IMPORTANT]
>  该环回方案不支持签名协议。 在此环回方案中，签名消息将验证失败，这是因为 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 只允许配置一个带有签名证书的参与方。 本组织和合作伙伴组织不能使用相同的签名证书。 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 中的这个限制条件是为了能够通过使用签名证书来唯一标识一个参与方。 因此，两个 BizTalk 参与方不能共享相同的证书。  
  
 有关环回实现的详细信息，请参阅[环回教程](../../adapters-and-accelerators/accelerator-rosettanet/loopback-tutorial.md)。  
  
## <a name="using-loopback-with-0a1-agreements"></a>将 Loopback 与 0A1 协议一起使用  
 你可以配置一个生成 0A1（失败通知）消息的环回方案。 为此，必须为本组织创建以下协议：请求操作-消息协议、发起方 0A1 协议和响应方 0A1 协议。 然后必须对这些协议运行 Loopback 实用工具以为合作伙伴组织创建以下协议：请求操作-消息协议、发起方 0A1 协议和响应方 0A1 协议。 这一步是必需的，因为不能使用 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理控制台来创建这些协议。  
  
 完整的一组协议必须包括用于以下消息的协议。 例如，如果操作消息是 3A4，则应包括以下协议：  
  
-   Home_to_Partner_3A4（操作消息）协议。 该协议启动从 HOME 组织到 PARTNER 组织的操作消息 PIP。  
  
-   Home_to_Partner_Initiator_0A1 协议。 该协议启动从 HOME 组织到 PARTNER 组织的 PIP 0A1。  
  
-   Home_to_Partner_Responder_0A1 协议。 该协议接收从 PARTNER 组织到 HOME 组织的 PIP 0A1。  
  
-   Loopback:Home_to_Partner_3A4（响应消息）协议。 该协议接收从 HOME 组织到 PARTNER 组织的 PIP 3A4。  
  
-   Loopback:Home_to_Partner_Responder_0A1 协议。 该协议启动从 PARTNER 组织到 HOME 组织的 PIP 0A1。  
  
-   Loopback:Home_to_Partner_Initiator_0A1。 该协议接收从 HOME 组织到 PARTNER 组织的 PIP 0A1。  
  
## <a name="creating-the-loopback-agreements-for-0a1-messages"></a>创建 0A1 消息的环回协议  
 若要创建一组完整的协议，必须使用 Loopback 实用工具来创建合作伙伴的操作-消息协议和 0A1 协议。 下面的表给出了生成合作伙伴环回协议所需的 Loopback 操作。 本主题在下面的表中使用 3A4 消息作为示例。  
  
|步骤|HOME 协议|  
|----------|---------------------|  
|1, 4|Home_to_Partner_3A4<br /><br /> 本组织：HOME<br /><br /> 合作伙伴组织：PARTNER<br /><br /> 本组织角色：发起方<br /><br /> 0A1 协议：Home_to_Partner_Initiator_0A1<br /><br /> 说明：启动从 HOME 到 PARTNER 的 PIP 3A4 的协议|  
|2|Home_to_Partner_Initiator_0A1<br /><br /> 本方：Home<br /><br /> 合作伙伴：Partner<br /><br /> 角色：发起方<br /><br /> 说明：启动从 HOME 到 PARTNER 的 PIP 0A1 的协议|  
|3|Home_to_Partner_Responder_0A1<br /><br /> 本方：Home<br /><br /> 合作伙伴：Partner<br /><br /> 角色：响应方<br /><br /> 说明：接收从 PARTNER 到 HOME 的 PIP 0A1 的协议|  
  
|步骤|PARTNER 协议（使用 Loopback.exe 镜像的协议）|  
|----------|--------------------------------------------------------|  
|7|Loopback:Home_to_Partner_3A4<br /><br /> 本方：Partner<br /><br /> 合作伙伴：Home<br /><br /> 角色：响应方<br /><br /> 0A1 协议：Loopback:Home_to_Partner_Responder_0A1<br /><br /> 说明：接收从 HOME 到 PARTNER 的 PIP 3A4 的协议<br /><br /> 创建它的 Loopback 命令：Loopback /mirror Home_to_Partner_3A4 /NoF Loopback:Home_to_Partner_Responder_0A1|  
|5|Loopback:Home_to_Partner_Responder_0A1<br /><br /> 本方：Partner<br /><br /> 合作伙伴：Home<br /><br /> 角色：发起方<br /><br /> 说明：启动从 PARTNER 到 HOME 的 PIP 0A1 的协议<br /><br /> 创建它的 Loopback 命令：Loopback /mirror Home_to_Partner_Responder_0A1|  
|6|Loopback:Home_to_Partner_Initiator_0A1<br /><br /> 本方：Partner<br /><br /> 合作伙伴：Home<br /><br /> 角色：响应方<br /><br /> 说明：接收从 HOME 到 PARTNER 的 PIP 0A1 的协议<br /><br /> 创建它的 Loopback 命令：Loopback /mirror Home_to_Partner_Initiator_0A1|  
  
 在以下过程中需运行这些表中的 Loopback 命令。  
  
#### <a name="to-create-the-agreements-for-a-loopback-scenario-using-0a1-messages"></a>为使用 0A1 消息的环回方案创建协议  
  
1.  在 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理控制台中，创建一个用于由本组织发送的请求操作消息的协议。  
  
2.  创建一个用于由本组织发送的发起方 0A1 消息的协议，并执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**我的组织**|设为本组织。|  
    |**伙伴组织**|设为合作伙伴。|  
    |**主角色**|设置为**PIP 失败通知程序 （发起程序）**。|  
  
3.  使用 [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] 管理控制台创建一个用于由本组织发送的响应方 0A1 消息的协议，并执行以下操作：  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**我的组织**|设为本组织。|  
    |**伙伴组织**|设为合作伙伴。|  
    |**主角色**|设置为**失败报表管理员 （响应方）**。|  
  
4.  使用[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台中，设置**0A1 协议**本组织的请求操作消息的名称的协议本组织的发起程序 0A1 协议的属性。  
  
5.  使用 Loopback 实用工具创建用于由合作伙伴组织发送的发起方 0A1 消息的协议。 为此，需要镜像本组织的响应方 0A1 协议。 这将创建新的 0A1 协议同名**环回：\<0A1 协议名称\>**。 `My organization`属性设置为合作伙伴，`Partner organization`属性设置为在主组织和`Home role`属性是**PIP 失败通知程序 （发起程序）**。  
  
6.  使用 Loopback 实用工具创建用于合作伙伴组织的响应方 0A1 消息的协议。 为此，需要镜像本组织的 0A1 发起方协议。 这将创建新的 0A1 协议同名**环回：\<0A1 协议名称\>**。 `My organization`属性设置为合作伙伴，`Partner organization`属性设置为在主组织和`Home role`属性是**失败报表管理员 （响应方）**。  
  
7.  使用 Loopback 实用工具创建用于合作伙伴组织的响应操作消息的协议。 在此命令中，还必须将 0A1 协议属性设置为合作伙伴的响应方 0A1 协议。 执行此操作通过镜像家庭的组织中，请求操作消息协议，并使用 **/NoF**切换与合作伙伴的响应方 0A1 协议的名称。 这将创建新的响应操作消息协议同名**环回：\<协议名称\>**。 将 `My organization` 属性设置为合作伙伴，0A1 协议属性设置为合作伙伴的响应方 0A1 协议。  
  
## <a name="see-also"></a>请参阅  
 [实用程序](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [Loopback 教程](../../adapters-and-accelerators/accelerator-rosettanet/loopback-tutorial.md)
