---
title: Loopback | Microsoft Docs
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
ms.openlocfilehash: f1cc2a6c1434812f876ea71881890a08d165f471
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65283316"
---
# <a name="loopback"></a>Loopback
使用 Loopback 实用工具来自动生成环回协议，它是本组织到合作伙伴协议的镜像副本。 这允许您在单台计算机上执行本组织合作伙伴和合作伙伴主页消息交换。 用于带有 0A1 消息的方案或不带 0A1 消息的方案，可以使用此实用工具。 可以创建环回协议的操作-消息 (非 0A1) 协议或 0A1 协议。  

 此外可以使用实用工具来登记或取消登记发件人角色的本组织。 当你使用该实用工具启用本组织时，它将创建两个发送端口，\<家庭\>。异步和\<主页\>。同步组织用来与其合作伙伴进行通信。  

## <a name="location-in-sdk"></a>在 SDK 中的位置  
 \<*drive*\>\ Program Files (x86)\Microsoft BizTalk \<version\> Accelerator for RosettaNet\SDK\  

## <a name="running-loopback"></a>运行 Loopback  

#### <a name="to-run-loopback"></a>若要运行 Loopback  

1.  打开命令提示符。  

2.  将移动到\<*驱动器*\>\ Program Files (x86) \Microsoft BizTalk\<版本\>Accelerator for RosettaNet\SDK\\。  

3.  在命令提示符处，键入**Loopback**，键入必需的和适当的开关，，然后按 ENTER。  

## <a name="syntax-for-loopback"></a>Loopback 的语法  
 下面显示的语法，用于启动此命令行实用程序：  

```  
Loopback [/enable|/disable <home_organization>] [/mirror|/unmirror <agreement_name>] [/NoF <0A1_agreement>]  
```  

## <a name="syntax-description"></a>语法说明  
 下表描述了 Loopback 实用工具使用的语法的每个部分。  

|**语法**|**说明**|  
|----------------|---------------------|  
|**enable**|登记在 < home_organization > 中指定的发件人角色的组织。 它将创建两个发送端口，\<主页\>。异步和\<主页\>。同步合作伙伴用来返回到本组织进行通信。|  
|**disable**|取消登记发件人角色的本组织。|  
|**home_organization**|要登记或取消登记发件人角色的伙伴。|  
|**mirror**|创建环回协议中指定的协议上基于\< **agreement_name**\>。|  
|**unmirror**|删除环回协议中指定的协议上基于\< **agreement_name\>**。|  
|**agreement_name**|要镜像或取消环回方案中的协议。|  
|**NoF**|集**0A1 协议**属性的情况下为 Loopback 实用工具镜像的操作-消息协议\<0A1_agreement\>。 一个 **/NoF**开关只能添加到还包含的 Loopback 命令 **/镜像**切换。|  
|**0A1_agreement**|Agreement_name 的镜像协议使用 0A1 协议。 本协议生成通过镜像响应方 0A1 协议。|  

## <a name="remarks"></a>备注  
 Loopback 实用工具切换角色在创建环回协议。 如果某组织在原始协议中是本组织，该实用程序可让合作伙伴组织环回协议中。 同样，如果某组织在原始协议中是合作伙伴组织，该实用程序可让本组织环回协议中。 实用工具还会切换本组织角色属性的设置。 如果本组织角色属性是发起方在原始协议中，该实用工具会使它对响应方，反之亦然。 所有其他属性保持不变。  

 Loopback 实用工具名称与原始协议，前面有同名的环回协议"环回:"。 为避免混淆，不要命名"loopback"开头的协议。  

 如果已为其生成环回协议的协议上运行该实用程序，该实用工具将取消镜像现有的环回协议，并创建新的环回协议。  

 您需要的 Loopback 实用工具，因为无法创建镜像的协议内[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台。 无法创建中的协议[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台中为其本组织、 合作伙伴组织和本组织属性被颠倒，并将所有其他字段都与现有协议的字段相同。 同样，[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]不支持更改环回协议直接在控制台中的。 如果你尝试在控制台中打开环回协议，你将收到错误。 如果必须对环回协议进行任何更改，更改起始协议，然后对其再次以重新生成环回协议运行 Loopback 实用工具。  

> [!IMPORTANT]
>  环回方案不支持签名的协议。 在此方案中，已签名的消息验证将失败，因为[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]可以只有一个参与方配置签名证书。 本组织和合作伙伴组织不能使用相同的签名证书。 这是中的限制[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]来唯一标识参与方使用签名证书。 因此，没有两个 BizTalk 参与方可以共享相同的证书。  

 有关环回实现的详细信息，请参阅[Loopback 教程](../../adapters-and-accelerators/accelerator-rosettanet/loopback-tutorial.md)。  

## <a name="using-loopback-with-0a1-agreements"></a>使用 Loopback 与 0A1 协议  
 你可以配置生成 0A1 （失败通知） 消息的环回方案。 若要执行此操作，必须创建本组织的以下协议： 请求操作-消息协议、 发起方 0A1 协议和响应方 0A1 协议。 然后必须对这些协议创建合作伙伴组织的以下协议运行 Loopback 实用工具： 响应操作-消息协议、 发起方 0A1 协议和响应方 0A1 协议。 这是必需的因为不能使用[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台来创建这些协议。  

 完成组协议必须包括以下消息的协议。 图中，对于操作消息是 3A4:  

-   Home_to_Partner_3A4 （操作消息） 协议。 该协议启动的操作消息 PIP 从 HOME 组织到 PARTNER 组织。  

-   Home_to_Partner_Initiator_0A1 协议。 该协议启动从 HOME 组织到 PARTNER 组织的 PIP 0A1。  

-   Home_to_Partner_Responder_0A1 协议。 该协议接收从合作伙伴组织到 HOME 组织的 PIP 0A1。  

-   Loopback: home_to_partner_3a4 （响应消息） 协议。 该协议接收从 HOME 组织到 PARTNER 组织的 PIP 3A4。  

-   Loopback:Home_to_Partner_Responder_0A1 协议。 该协议启动从 PARTNER 组织到 HOME 组织的 PIP 0A1。  

-   Loopback:Home_to_Partner_Initiator_0A1. 该协议接收从 HOME 组织到 PARTNER 组织的 PIP 0A1。  

## <a name="creating-the-loopback-agreements-for-0a1-messages"></a>创建 0A1 消息的 Loopback 协议  
 若要创建一组完整的协议，必须使用 Loopback 实用工具创建合作伙伴上的操作-消息和 0A1 协议。 下表显示了生成合作伙伴所需的 Loopback 操作环回协议。 为了进行说明，本主题的表中使用 3A4 消息。  

|步骤|HOME 协议|  
|----------|---------------------|  
|1, 4|Home_to_Partner_3A4<br /><br /> 本组织：Home<br /><br /> 合作伙伴组织：PARTNER<br /><br /> 本组织角色：Initiator<br /><br /> 0A1 协议：Home_to_Partner_Initiator_0A1<br /><br /> 说明:启动从 HOME 到 PARTNER 的 PIP 3A4 的协议|  
|2|Home_to_Partner_Initiator_0A1<br /><br /> 主页：主页<br /><br /> 合作伙伴：Partner<br /><br /> 角色：Initiator<br /><br /> 说明:启动从 HOME 到 PARTNER 的 PIP 0A1 的协议|  
|3|Home_to_Partner_Responder_0A1<br /><br /> 主页：主页<br /><br /> 合作伙伴：Partner<br /><br /> 角色：响应方<br /><br /> 说明:接收从 PARTNER 到 HOME 的 PIP 0A1 的协议|  

|步骤|合作伙伴协议 （使用 Loopback.exe 镜像）|  
|----------|--------------------------------------------------------|  
|7|Loopback:Home_to_Partner_3A4<br /><br /> 主页：Partner<br /><br /> 合作伙伴：主页<br /><br /> 角色：响应方<br /><br /> 0A1 协议：Loopback:Home_to_Partner_Responder_0A1<br /><br /> 说明:接收从 HOME 到 PARTNER 的 PIP 3A4 的协议<br /><br /> Loopback 命令创建它：Loopback /mirror Home_to_Partner_3A4 /NoF Loopback:Home_to_Partner_Responder_0A1|  
|5|Loopback:Home_to_Partner_Responder_0A1<br /><br /> 主页：Partner<br /><br /> 合作伙伴：主页<br /><br /> 角色：Initiator<br /><br /> 说明:启动从 PARTNER 到 HOME 的 PIP 0A1 的协议<br /><br /> Loopback 命令创建它：Loopback /mirror Home_to_Partner_Responder_0A1|  
|6|Loopback:Home_to_Partner_Initiator_0A1<br /><br /> 主页：Partner<br /><br /> 合作伙伴：主页<br /><br /> 角色：响应方<br /><br /> 说明:接收从 HOME 到 PARTNER 的 PIP 0A1 的协议<br /><br /> Loopback 命令创建它：Loopback /mirror Home_to_Partner_Initiator_0A1|  

 以下过程在这些表中运行的 Loopback 命令。  

#### <a name="to-create-the-agreements-for-a-loopback-scenario-using-0a1-messages"></a>若要为使用 0A1 消息的环回方案创建协议  

1. 在[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台中，创建用于由本组织发送的请求操作消息的协议。  

2. 创建用于由本组织发送的发起方 0A1 消息的协议，执行以下操作：  


   |         使用此选项         |                  执行的操作                  |
   |--------------------------|----------------------------------------------|
   |   **我的组织**    |        将设置为本组织。         |
   | **合作伙伴组织** |             设置为合作伙伴。              |
   |      **本组织角色**       | 设置为**PIP 失败通知方 （发起方）**。 |


3. 使用[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台中，创建一个协议响应方 0A1 消息发送到本组织，并执行以下操作：  


   |         使用此选项         |                      执行的操作                      |
   |--------------------------|------------------------------------------------------|
   |   **我的组织**    |            将设置为本组织。             |
   | **合作伙伴组织** |                 设置为合作伙伴。                  |
   |      **本组织角色**       | 设置为**失败报告管理员 （响应方）**。 |


4. 使用[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台中，设置**0A1 协议**本组织的请求操作-消息协议的名称的本组织的发起方 0A1 协议属性。  

5. 使用 Loopback 实用工具创建一个用于由合作伙伴组织发送的发起方 0A1 消息的协议。 执行此操作通过镜像响应方 0A1 协议为本组织。 这将创建同名的新 0A1 协议**环回：\<0A1 协议名称\>**。 `My organization`属性设置为合作伙伴`Partner organization`属性设置为本组织，并`Home role`属性是**PIP 失败通知方 （发起方）**。  

6. 使用 Loopback 实用工具创建合作伙伴组织的响应方 0A1 消息的协议。 执行此操作，需要镜像本组织的 0A1 发起方协议。 这将创建同名的新 0A1 协议**环回：\<0A1 协议名称\>**。 `My organization`属性设置为合作伙伴`Partner organization`属性设置为本组织，并`Home role`属性是**失败报告管理员 （响应方）**。  

7. 使用 Loopback 实用工具创建合作伙伴组织的响应操作消息的协议。 在同一命令中，你必须设置为合作伙伴的响应方 0A1 协议的 0A1 协议属性。 执行此操作通过镜像本组织的请求操作-消息协议，并使用 **/NoF**开关与合作伙伴的响应方 0A1 协议的名称。 这将创建新的响应操作-消息协议同名**Loopback:\<协议名称\>**。 `My organization`属性设置为合作伙伴，0A1 协议属性设置为合作伙伴的响应方 0A1 协议。  

## <a name="see-also"></a>请参阅  
 [实用程序](../../adapters-and-accelerators/accelerator-rosettanet/utilities1.md)   
 [Loopback 教程](../../adapters-and-accelerators/accelerator-rosettanet/loopback-tutorial.md)
