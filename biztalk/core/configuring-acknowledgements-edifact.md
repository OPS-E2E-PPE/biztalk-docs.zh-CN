---
title: 配置确认 (EDIFACT) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9436feb7-4c29-4b7c-b5c2-991660e6c1a9
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fe376437c2d6657acb98d548c2c1373b050d599
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233493"
---
# <a name="configuring-acknowledgements-edifact"></a><span data-ttu-id="e8311-102">配置确认(EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="e8311-102">Configuring Acknowledgements (EDIFACT)</span></span>
<span data-ttu-id="e8311-103">在合作伙伴协议中，可以指定将何种类型的确认返回给参与方以及在发送确认时使用何种发送端口。</span><span class="sxs-lookup"><span data-stu-id="e8311-103">In the partner agreement, you can specify what type of acknowledgment to return to a party and what kind of send port to use in sending the acknowledgment.</span></span> <span data-ttu-id="e8311-104">还可以指定是否对确认进行批处理、为确认使用哪个起始事务集参考编号以及是否为接受的事务集生成 SG1/SG4 循环。</span><span class="sxs-lookup"><span data-stu-id="e8311-104">You also specify whether to batch an acknowledgment, what the starting transaction set reference number is for the acknowledgment, and whether SG1/SG4 loops are generated for accepted transaction sets.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="e8311-105">以下属性禁用此页上，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="e8311-105">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  -   <span data-ttu-id="e8311-106">**生成 SG1/SG4 循环，用于接受的事务集 （如果未选中，循环将生成仅当 UCM.5 是否不等于 7）**。</span><span class="sxs-lookup"><span data-stu-id="e8311-106">**Generate SG1/SG4 loop for accepted transaction sets (If unchecked, loop will be generated only if UCM.5 is not equal to 7)**.</span></span>  
>   
>  <span data-ttu-id="e8311-107">仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="e8311-107">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="e8311-108">例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="e8311-108">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e8311-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="e8311-109">Prerequisites</span></span>  
 <span data-ttu-id="e8311-110">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="e8311-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-edifact-ack-contrl-properties"></a><span data-ttu-id="e8311-111">配置 EDIFACT 确认 (CONTRL) 属性</span><span class="sxs-lookup"><span data-stu-id="e8311-111">To configure EDIFACT ACK (CONTRL) properties</span></span>  
  
1.  <span data-ttu-id="e8311-112">创建 EDIFACT 编码协议中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。</span><span class="sxs-lookup"><span data-stu-id="e8311-112">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="e8311-113">若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="e8311-113">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="e8311-114">单向协议选项卡上，在**交换设置**部分中，单击**确认**。</span><span class="sxs-lookup"><span data-stu-id="e8311-114">On a one-way agreement tab, under **Interchange Settings** section, click **Acknowledgements**.</span></span>  
  
3.  <span data-ttu-id="e8311-115">在**EDIFACT ACK （控件） 部分**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e8311-115">In the **EDIFACT ACK (Control) section**, do the following:</span></span>  
  
    1.  <span data-ttu-id="e8311-116">选择**收到预期消息 (CONTRL)** 可向交换发件人返回技术 (CONTRL) 确认。</span><span class="sxs-lookup"><span data-stu-id="e8311-116">Select **Receipt of message (CONTRL) expected** to return a technical (CONTRL) acknowledgment to the interchange sender.</span></span> <span data-ttu-id="e8311-117">如果**收到预期消息 (CONTRL)** ，则选择**执行批量收到消息 (CONTRL) 消息**分别发送每个确认或离开清除进行批处理确认。</span><span class="sxs-lookup"><span data-stu-id="e8311-117">If **Receipt of message (CONTRL) expected** is selected, select **Do not batch receipt of message (CONTRL) message** to send each acknowledgment separately, or leave cleared to batch the acknowledgments.</span></span>  
  
    2.  <span data-ttu-id="e8311-118">选择**确认 (CONTRL) 预期**可向交换发件人返回功能 (CONTRL) 确认。</span><span class="sxs-lookup"><span data-stu-id="e8311-118">Select **Acknowledgement (CONTRL) expected** to return a functional (CONTRL) acknowledgment to the interchange sender.</span></span> <span data-ttu-id="e8311-119">如果**确认 (CONTRL) 预期**，则选择**执行批量确认 (CONTRL)** 分别发送每个功能确认或离开清除进行批处理功能确认。</span><span class="sxs-lookup"><span data-stu-id="e8311-119">If **Acknowledgement (CONTRL) expected** is selected, select **Do not batch Acknowledgement (CONTRL)** to send each functional acknowledgment separately, or leave cleared to batch the functional acknowledgments.</span></span>  
  
4.  <span data-ttu-id="e8311-120">在**事务集状态接受报告**部分，若要强制在功能 CONTRL 确认中为接受的事务集生成 SG1/SG4 循环选择**生成 SG1/SG4 循环接受事务集 （如果未选中，循环将生成仅当 UCM.5 是否不等于 7）**。</span><span class="sxs-lookup"><span data-stu-id="e8311-120">In the **Transaction set status acceptance reporting** section, to force generation of SG1/SG4 loops in functional CONTRL acknowledgments for accepted transaction sets, select **Generate SG1/SG4 loop for accepted transaction sets (If unchecked, loop will be generated only if UCM.5 is not equal to 7)**.</span></span> <span data-ttu-id="e8311-121">有关 SG1/SG4 循环的详细信息，请参阅[作为功能确认的 EDIFACT CONTRL 消息](../core/edifact-contrl-message-as-functional-acknowledgment.md)。</span><span class="sxs-lookup"><span data-stu-id="e8311-121">For more information about SG1/SG4 loops, see [EDIFACT CONTRL Message as Functional Acknowledgment](../core/edifact-contrl-message-as-functional-acknowledgment.md).</span></span>  
  
5.  <span data-ttu-id="e8311-122">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="e8311-122">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8311-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8311-123">See Also</span></span>  
 [<span data-ttu-id="e8311-124">配置交换设置 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="e8311-124">Configuring Interchange Settings (EDIFACT)</span></span>](../core/configuring-interchange-settings-edifact.md)