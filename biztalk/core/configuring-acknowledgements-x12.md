---
title: 配置确认 (X12) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eec2dbff-5d04-4a38-bad0-33d040b6dd12
caps.latest.revision: 26
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edec872f4055bb2c06772d361f18345d4a4be2d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233621"
---
# <a name="configuring-acknowledgements-x12"></a><span data-ttu-id="8d7a5-102">配置确认 (X 12)</span><span class="sxs-lookup"><span data-stu-id="8d7a5-102">Configuring Acknowledgements (X12)</span></span>
<span data-ttu-id="8d7a5-103">在合作伙伴协议中，您可以指定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 生成确认的方式，以响应从参与方接收的 X12 编码的交换，以及返回到参与方的确认类型。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-103">In the partner agreement, you can specify how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates acknowledgments in response to X12-encoded interchanges received from the party and what type of acknowledgment to return to a party.</span></span> <span data-ttu-id="8d7a5-104">您还可以指定是否批处理确认，以及是否为接收的事务集生成 AK2 循环。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-104">You can also specify whether to batch an acknowledgement and whether AK2 loops are generated for accepted transaction sets.</span></span> <span data-ttu-id="8d7a5-105">本部分提供如何执行操作的说明。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-105">This section provides instructions on how to do so.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8d7a5-106">此处所述的确认属性同样适用于 HIPAA 确认。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-106">The acknowledgement properties described here apply also for HIPAA acknowledgements.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8d7a5-107">以下属性禁用此页上，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-107">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  -   <span data-ttu-id="8d7a5-108">**包括 AK2 循环，用于接受的事务集 （如果未选中，循环将生成仅当 AK501 是否不等于 A）**。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-108">**Include AK2 loop for accepted transaction sets (if unchecked, loop will be generated only if AK501 is not equal to A)**.</span></span>  
>   
>  <span data-ttu-id="8d7a5-109">仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-109">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="8d7a5-110">例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-110">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8d7a5-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="8d7a5-111">Prerequisites</span></span>  
 <span data-ttu-id="8d7a5-112">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-112">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-x12-ack-properties"></a><span data-ttu-id="8d7a5-113">配置 X12 确认属性</span><span class="sxs-lookup"><span data-stu-id="8d7a5-113">To configure X12 ACK properties</span></span>  
  
1.  <span data-ttu-id="8d7a5-114">创建 X12 编码协议中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-114">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="8d7a5-115">若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-115">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="8d7a5-116">单向协议选项卡上，在**交换设置**，单击**确认**。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-116">On a one-way agreement tab, under **Interchange Settings**, click **Acknowledgements**.</span></span>  
  
3.  <span data-ttu-id="8d7a5-117">选择**预期的 TA1**可向交换发件人返回技术 (TA1) 确认。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-117">Select **TA1 Expected** to return a technical (TA1) acknowledgment to the interchange sender.</span></span> <span data-ttu-id="8d7a5-118">如果选择，选择**执行批量 TA1**分别发送每个技术确认或离开清除进行批处理的技术确认此复选框。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-118">If selected, select **Do not batch TA1** to send each technical acknowledgment separately, or leave the check box cleared to batch the technical acknowledgments.</span></span>  
  
4.  <span data-ttu-id="8d7a5-119">选择**997 预期**可向交换发件人返回功能 (997) 确认。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-119">Select **997 Expected** to return a functional (997) acknowledgment to the interchange sender.</span></span> <span data-ttu-id="8d7a5-120">如果选择，选择**执行批量 997**分别发送每个功能确认或离开清除进行批处理功能确认此复选框。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-120">If selected, select **Do not batch 997** to send each functional acknowledgment separately, or leave the check box cleared to batch the functional acknowledgments.</span></span>  
  
5.  <span data-ttu-id="8d7a5-121">若要启用在 997 确认中为接受的事务集生成 AK2 循环，请选择**包括 AK2 循环，用于接受的事务集 （如果未选中，循环将生成仅当 AK501 是否不等于 A）**。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-121">To enable generation of AK2 loops in 997 acknowledgments for accepted transaction sets, select **Include AK2 loop for accepted transaction sets (if unchecked, loop will be generated only if AK501 is not equal to A)**.</span></span> <span data-ttu-id="8d7a5-122">有关 AK2 循环的详细信息，请参阅[X12 997 确认](../core/x12-997-acknowledgment.md)。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-122">For more information about AK2 loops, see [X12 997 Acknowledgment](../core/x12-997-acknowledgment.md).</span></span>  
  
6.  <span data-ttu-id="8d7a5-123">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="8d7a5-123">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d7a5-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d7a5-124">See Also</span></span>  
 [<span data-ttu-id="8d7a5-125">配置交换设置 (X12)</span><span class="sxs-lookup"><span data-stu-id="8d7a5-125">Configuring Interchange Settings (X12)</span></span>](../core/configuring-interchange-settings-x12.md)