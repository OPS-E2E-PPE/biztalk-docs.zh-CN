---
title: 配置确认 (EDIFACT) |Microsoft Docs
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
ms.openlocfilehash: 869d65f81c280e608b636d4bd9f1292d47d47172
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356347"
---
# <a name="configuring-acknowledgements-edifact"></a><span data-ttu-id="23eaf-102">配置确认 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="23eaf-102">Configuring Acknowledgements (EDIFACT)</span></span>
<span data-ttu-id="23eaf-103">在合作伙伴协议中，可以指定哪种类型的确认返回给参与方以及什么类型的发送端口以使用在发送确认。</span><span class="sxs-lookup"><span data-stu-id="23eaf-103">In the partner agreement, you can specify what type of acknowledgment to return to a party and what kind of send port to use in sending the acknowledgment.</span></span> <span data-ttu-id="23eaf-104">您还指定是否批处理确认哪些的起始事务集参考编号对，是是否为接受的事务集生成 SG1/SG4 循环。</span><span class="sxs-lookup"><span data-stu-id="23eaf-104">You also specify whether to batch an acknowledgment, what the starting transaction set reference number is for the acknowledgment, and whether SG1/SG4 loops are generated for accepted transaction sets.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="23eaf-105">以下属性禁用此页上，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="23eaf-105">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
> 
> - <span data-ttu-id="23eaf-106">**生成为接受的事务集 SG1/SG4 循环 （如果未选中，将生成循环仅当 UCM.5 不等于 7）**。</span><span class="sxs-lookup"><span data-stu-id="23eaf-106">**Generate SG1/SG4 loop for accepted transaction sets (If unchecked, loop will be generated only if UCM.5 is not equal to 7)**.</span></span>  
> 
>   <span data-ttu-id="23eaf-107">仅在与参与方所发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="23eaf-107">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="23eaf-108">例如，如果创建两个参与方 Party A 和参与方 B，并且对于参与方 A 清除该复选框，上述列表中的属性上禁用**参与方 A-> 参与方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="23eaf-108">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="23eaf-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="23eaf-109">Prerequisites</span></span>  
 <span data-ttu-id="23eaf-110">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="23eaf-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-edifact-ack-contrl-properties"></a><span data-ttu-id="23eaf-111">若要配置 EDIFACT 确认 (CONTRL) 属性</span><span class="sxs-lookup"><span data-stu-id="23eaf-111">To configure EDIFACT ACK (CONTRL) properties</span></span>  
  
1.  <span data-ttu-id="23eaf-112">创建 EDIFACT 编码协议，如中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。</span><span class="sxs-lookup"><span data-stu-id="23eaf-112">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="23eaf-113">若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="23eaf-113">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="23eaf-114">在单向协议选项卡下**交换设置**部分中，单击**确认**。</span><span class="sxs-lookup"><span data-stu-id="23eaf-114">On a one-way agreement tab, under **Interchange Settings** section, click **Acknowledgements**.</span></span>  
  
3.  <span data-ttu-id="23eaf-115">在中**EDIFACT 确认 (Control) 部分**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="23eaf-115">In the **EDIFACT ACK (Control) section**, do the following:</span></span>  
  
    1.  <span data-ttu-id="23eaf-116">选择**预期接收消息 (CONTRL)** 向交换发件人返回技术 (CONTRL) 确认。</span><span class="sxs-lookup"><span data-stu-id="23eaf-116">Select **Receipt of message (CONTRL) expected** to return a technical (CONTRL) acknowledgment to the interchange sender.</span></span> <span data-ttu-id="23eaf-117">如果**预期接收消息 (CONTRL)** ，则选择**进行批处理的消息 (CONTRL) 消息的接收**可单独发送每个确认，否则将对确认进行批处理。</span><span class="sxs-lookup"><span data-stu-id="23eaf-117">If **Receipt of message (CONTRL) expected** is selected, select **Do not batch receipt of message (CONTRL) message** to send each acknowledgment separately, or leave cleared to batch the acknowledgments.</span></span>  
  
    2.  <span data-ttu-id="23eaf-118">选择**确认 (CONTRL) 预期**向交换发件人返回功能 (CONTRL) 确认。</span><span class="sxs-lookup"><span data-stu-id="23eaf-118">Select **Acknowledgement (CONTRL) expected** to return a functional (CONTRL) acknowledgment to the interchange sender.</span></span> <span data-ttu-id="23eaf-119">如果**确认 (CONTRL) 预期**，则选择**不批确认 (CONTRL)** 可单独发送每个功能确认，否则将进行批处理功能确认。</span><span class="sxs-lookup"><span data-stu-id="23eaf-119">If **Acknowledgement (CONTRL) expected** is selected, select **Do not batch Acknowledgement (CONTRL)** to send each functional acknowledgment separately, or leave cleared to batch the functional acknowledgments.</span></span>  
  
4.  <span data-ttu-id="23eaf-120">在中**事务集状态接受报告**部分中，若要强制在功能 CONTRL 确认中为接受的事务集 SG1/SG4 循环的生成选择**生成 SG1/SG4 循环接受事务集 （如果未选中，将生成循环仅当 UCM.5 不等于 7）**。</span><span class="sxs-lookup"><span data-stu-id="23eaf-120">In the **Transaction set status acceptance reporting** section, to force generation of SG1/SG4 loops in functional CONTRL acknowledgments for accepted transaction sets, select **Generate SG1/SG4 loop for accepted transaction sets (If unchecked, loop will be generated only if UCM.5 is not equal to 7)**.</span></span> <span data-ttu-id="23eaf-121">有关 SG1/SG4 循环的详细信息，请参阅[作为功能确认的 EDIFACT CONTRL 消息](../core/edifact-contrl-message-as-functional-acknowledgment.md)。</span><span class="sxs-lookup"><span data-stu-id="23eaf-121">For more information about SG1/SG4 loops, see [EDIFACT CONTRL Message as Functional Acknowledgment](../core/edifact-contrl-message-as-functional-acknowledgment.md).</span></span>  
  
5.  <span data-ttu-id="23eaf-122">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="23eaf-122">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23eaf-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="23eaf-123">See Also</span></span>  
 [<span data-ttu-id="23eaf-124">配置交换设置 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="23eaf-124">Configuring Interchange Settings (EDIFACT)</span></span>](../core/configuring-interchange-settings-edifact.md)