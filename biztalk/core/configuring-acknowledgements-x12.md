---
title: 配置确认 (X12) |Microsoft Docs
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
ms.openlocfilehash: 9cd9497c6367ae757206ba91d60575476fbfd05e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356322"
---
# <a name="configuring-acknowledgements-x12"></a><span data-ttu-id="d453a-102">配置确认 (X 12)</span><span class="sxs-lookup"><span data-stu-id="d453a-102">Configuring Acknowledgements (X12)</span></span>
<span data-ttu-id="d453a-103">在合作伙伴协议中，您可以指定如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]响应从参与方和类型的确认返回到参与方接收的 X12 编码交换而生成确认。</span><span class="sxs-lookup"><span data-stu-id="d453a-103">In the partner agreement, you can specify how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates acknowledgments in response to X12-encoded interchanges received from the party and what type of acknowledgment to return to a party.</span></span> <span data-ttu-id="d453a-104">此外可以指定是否批处理确认，以及是否为接受的事务集生成 AK2 循环。</span><span class="sxs-lookup"><span data-stu-id="d453a-104">You can also specify whether to batch an acknowledgement and whether AK2 loops are generated for accepted transaction sets.</span></span> <span data-ttu-id="d453a-105">本部分将说明了如何执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d453a-105">This section provides instructions on how to do so.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d453a-106">此处所述的确认属性同样适用于 HIPAA 确认。</span><span class="sxs-lookup"><span data-stu-id="d453a-106">The acknowledgement properties described here apply also for HIPAA acknowledgements.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="d453a-107">以下属性禁用此页上，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="d453a-107">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
> 
> - <span data-ttu-id="d453a-108">**为接受的事务集包含 AK2 循环 （如果未选中，将生成循环仅当 AK501 不等于 A）**。</span><span class="sxs-lookup"><span data-stu-id="d453a-108">**Include AK2 loop for accepted transaction sets (if unchecked, loop will be generated only if AK501 is not equal to A)**.</span></span>  
> 
>   <span data-ttu-id="d453a-109">仅在与参与方所发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="d453a-109">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="d453a-110">例如，如果创建两个参与方 Party A 和参与方 B，并且对于参与方 A 清除该复选框，上述列表中的属性上禁用**参与方 A-> 参与方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="d453a-110">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d453a-111">先决条件</span><span class="sxs-lookup"><span data-stu-id="d453a-111">Prerequisites</span></span>  
 <span data-ttu-id="d453a-112">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="d453a-112">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-x12-ack-properties"></a><span data-ttu-id="d453a-113">若要配置 X12 确认属性</span><span class="sxs-lookup"><span data-stu-id="d453a-113">To configure X12 ACK properties</span></span>  
  
1.  <span data-ttu-id="d453a-114">创建 X12 编码协议，如中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="d453a-114">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="d453a-115">若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="d453a-115">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="d453a-116">在单向协议选项卡下**交换设置**，单击**确认**。</span><span class="sxs-lookup"><span data-stu-id="d453a-116">On a one-way agreement tab, under **Interchange Settings**, click **Acknowledgements**.</span></span>  
  
3.  <span data-ttu-id="d453a-117">选择**预期的 TA1**向交换发件人返回技术 (TA1) 确认。</span><span class="sxs-lookup"><span data-stu-id="d453a-117">Select **TA1 Expected** to return a technical (TA1) acknowledgment to the interchange sender.</span></span> <span data-ttu-id="d453a-118">如果选择，选择**不对 TA1 进行批处理**单独发送每个技术确认，否则将技术确认进行批处理的清除此复选框。</span><span class="sxs-lookup"><span data-stu-id="d453a-118">If selected, select **Do not batch TA1** to send each technical acknowledgment separately, or leave the check box cleared to batch the technical acknowledgments.</span></span>  
  
4.  <span data-ttu-id="d453a-119">选择**预期的 997**向交换发件人返回功能 (997) 确认。</span><span class="sxs-lookup"><span data-stu-id="d453a-119">Select **997 Expected** to return a functional (997) acknowledgment to the interchange sender.</span></span> <span data-ttu-id="d453a-120">如果选择，选择**不对 997 进行批处理**单独发送每个功能确认，或清除对功能确认进行批处理复选框。</span><span class="sxs-lookup"><span data-stu-id="d453a-120">If selected, select **Do not batch 997** to send each functional acknowledgment separately, or leave the check box cleared to batch the functional acknowledgments.</span></span>  
  
5.  <span data-ttu-id="d453a-121">若要启用在 997 确认中为接受的事务集生成 AK2 循环，请选择**接受的事务集包含 AK2 循环 （如果未选中，将生成循环仅当 AK501 不等于 A）**。</span><span class="sxs-lookup"><span data-stu-id="d453a-121">To enable generation of AK2 loops in 997 acknowledgments for accepted transaction sets, select **Include AK2 loop for accepted transaction sets (if unchecked, loop will be generated only if AK501 is not equal to A)**.</span></span> <span data-ttu-id="d453a-122">有关 AK2 循环的详细信息，请参阅[X12 997 确认](../core/x12-997-acknowledgment.md)。</span><span class="sxs-lookup"><span data-stu-id="d453a-122">For more information about AK2 loops, see [X12 997 Acknowledgment](../core/x12-997-acknowledgment.md).</span></span>  
  
6.  <span data-ttu-id="d453a-123">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="d453a-123">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d453a-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="d453a-124">See Also</span></span>  
 [<span data-ttu-id="d453a-125">配置交换设置 (X12)</span><span class="sxs-lookup"><span data-stu-id="d453a-125">Configuring Interchange Settings (X12)</span></span>](../core/configuring-interchange-settings-x12.md)