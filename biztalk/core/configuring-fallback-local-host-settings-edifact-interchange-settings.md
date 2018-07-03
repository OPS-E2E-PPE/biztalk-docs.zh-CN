---
title: 配置回退本地主机设置 （EDIFACT-交换设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eecf5abb-9c12-44b0-bc58-94cb138515c3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a503a54e712026295c5df295e7ed6d8e2408a9a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001838"
---
# <a name="configuring-fallback-local-host-settings-edifact-interchange-settings"></a><span data-ttu-id="cb84a-102">配置回退本地主机设置（EDIFACT-交换设置）</span><span class="sxs-lookup"><span data-stu-id="cb84a-102">Configuring Fallback Local Host Settings (EDIFACT-Interchange Settings)</span></span>
<span data-ttu-id="cb84a-103">本地主机设置控制如何处理 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="cb84a-103">The local host settings govern how the EDI interchanges are processed.</span></span> <span data-ttu-id="cb84a-104">此页上的设置可以分为两个类别：接收方设置（用于传入交换）和发送方设置（用于传出交换）。</span><span class="sxs-lookup"><span data-stu-id="cb84a-104">The settings on this page can be divided into two categories – receiver’s settings (for incoming interchanges) and sender’s settings (for outgoing interchanges).</span></span> <span data-ttu-id="cb84a-105">作为接收方设置的一部分，您可以指定将要生成确认控制编号的方式。</span><span class="sxs-lookup"><span data-stu-id="cb84a-105">As part of the receiver’s settings, you can specify how the acknowledgement control number will be generated.</span></span> <span data-ttu-id="cb84a-106">作为发送方设置的一部分，可以指定为传出消息生成控制编号的方式。</span><span class="sxs-lookup"><span data-stu-id="cb84a-106">As part of the sender’s settings, you can specify how the control numbers are generated for outgoing messages.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cb84a-107">必要條件</span><span class="sxs-lookup"><span data-stu-id="cb84a-107">Prerequisites</span></span>  
 <span data-ttu-id="cb84a-108">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="cb84a-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-local-host--receivers-settings"></a><span data-ttu-id="cb84a-109">配置本地主机 – 接收方设置</span><span class="sxs-lookup"><span data-stu-id="cb84a-109">To configure local host – receiver’s settings</span></span>  
  
1. <span data-ttu-id="cb84a-110">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 后备设置**。</span><span class="sxs-lookup"><span data-stu-id="cb84a-110">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="cb84a-111">在中**EDIFACT 后备设置**对话框中**EDIFACT 协议页**选项卡上，在**交换设置**部分中，单击**本地主机设置**。</span><span class="sxs-lookup"><span data-stu-id="cb84a-111">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Interchange Settings** section, click **Local Host Settings**.</span></span>  
  
3. <span data-ttu-id="cb84a-112">在中**EDIFACT 确认**部分，若要指定要在确认中使用的事务集参考编号的前缀、 参考编号和后缀的范围输入一个值。</span><span class="sxs-lookup"><span data-stu-id="cb84a-112">In the **EDIFACT ACK** section, to designate the transaction set reference numbers to be used in an acknowledgment, enter a value for the prefix, a range of reference numbers, and suffix.</span></span>  
  
    <span data-ttu-id="cb84a-113">单击**重置**重置当前事务集参考编号为下限。</span><span class="sxs-lookup"><span data-stu-id="cb84a-113">Click **Reset** to reset the current transaction set reference number to the lower limit.</span></span> <span data-ttu-id="cb84a-114">选择**重置为下限值超出界限时**具有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将的参考编号重置为较低范围值限制，如果超出最大限制。</span><span class="sxs-lookup"><span data-stu-id="cb84a-114">Select **Reset to lower limit when out of bound** to have [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] reset the reference number to the lower range value limit if the maximum limit is exceeded.</span></span>  
  
### <a name="to-configure-local-host--senders-settings"></a><span data-ttu-id="cb84a-115">配置本地主机 – 发送方设置</span><span class="sxs-lookup"><span data-stu-id="cb84a-115">To configure local host – sender’s settings</span></span>  
  
1.  <span data-ttu-id="cb84a-116">有关**交换控制编号 (UNB5)**，输入要由 BizTalk Server 生成传出交换的交换控制编号的值的范围。</span><span class="sxs-lookup"><span data-stu-id="cb84a-116">For **Interchange control number (UNB5)**, enter a range of values for the interchange control number to be used by BizTalk Server in generating an outgoing interchange.</span></span> <span data-ttu-id="cb84a-117">输入一个最小为 1、最大为 999999999 的数值。</span><span class="sxs-lookup"><span data-stu-id="cb84a-117">Enter a numeric value with a minimum of 1 and a maximum of 999999999.</span></span> <span data-ttu-id="cb84a-118">此字段是必需字段。</span><span class="sxs-lookup"><span data-stu-id="cb84a-118">This is a mandatory field.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cb84a-119">第一个字段 (**UNB5.1**) 是前缀; 第二个和第三字段 (**UNB5.2**) 包含要用作交换控制编号; 和第四个字段的编号范围 (**UNB5.3**)是的后缀。</span><span class="sxs-lookup"><span data-stu-id="cb84a-119">The first field (**UNB5.1**) is the prefix; the second and third fields (**UNB5.2**) contain the range of numbers to use as the interchange control number; and the fourth field (**UNB5.3**) is the suffix.</span></span> <span data-ttu-id="cb84a-120">前缀和后缀是可选的；控制编号是必需的。</span><span class="sxs-lookup"><span data-stu-id="cb84a-120">The prefix and suffix are optional; the control number is required.</span></span> <span data-ttu-id="cb84a-121">每条新消息的控制编号是递增的；前缀和后缀保持不变。</span><span class="sxs-lookup"><span data-stu-id="cb84a-121">The control number is incremented for each new message; the prefix and suffix remain the same.</span></span> <span data-ttu-id="cb84a-122">控制编号最多 14 个字符，前缀和后缀最多 13 个字符，三个字段合起来最多 14 个字符。</span><span class="sxs-lookup"><span data-stu-id="cb84a-122">The maximum number of characters is 14 for the control number, 13 for the prefix and suffix, and 14 for all three fields combined.</span></span>  
    >   
    >  <span data-ttu-id="cb84a-123">若要将控制编号重置为指定的最小值，请单击**重置**按钮。</span><span class="sxs-lookup"><span data-stu-id="cb84a-123">To reset the control number to the minimum value specified, click the **Reset** button.</span></span> <span data-ttu-id="cb84a-124">检查**重置为下限值超出界限时**以自动重置为最小值超过了最大值。</span><span class="sxs-lookup"><span data-stu-id="cb84a-124">Check **Reset to lower limit when out of bound** to automatically reset to the minimum value if the maximum value is exceeded.</span></span>  
  
2.  <span data-ttu-id="cb84a-125">有关**组控制编号 (UNG5)**、 输入前缀、 参考编号范围和 BizTalk Server 应为它发送的第一个交换的组控制编号使用的后缀。</span><span class="sxs-lookup"><span data-stu-id="cb84a-125">For **Group control number (UNG5)**, enter the prefix, reference number range, and suffix that BizTalk Server should use for the group control number of the first interchange that it sends.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cb84a-126">第一个字段 (**UNG5.1**) 是前缀; 第二个和第三字段 (**UNG5.2**) 包含要用于组控制编号; 和第四个字段的编号范围 (**UNG5.3**) 是后缀。</span><span class="sxs-lookup"><span data-stu-id="cb84a-126">The first field (**UNG5.1**) is the prefix; the second and third fields (**UNG5.2**) contain the range of numbers to use for the group control number; and the fourth field (**UNG5.3**) is the suffix.</span></span> <span data-ttu-id="cb84a-127">前缀和后缀是可选的；控制编号是必需的。</span><span class="sxs-lookup"><span data-stu-id="cb84a-127">The prefix and suffix are optional; the control number is required.</span></span> <span data-ttu-id="cb84a-128">每条新消息的控制编号是递增的直到达到最大值；前缀和后缀保持不变。</span><span class="sxs-lookup"><span data-stu-id="cb84a-128">The control number is incremented for each new message until the maximum value is reached; the prefix and suffix remain the same.</span></span> <span data-ttu-id="cb84a-129">只允许使用数字中**UNG5.2**。</span><span class="sxs-lookup"><span data-stu-id="cb84a-129">Only numbers are allowed in **UNG5.2**.</span></span> <span data-ttu-id="cb84a-130">控制编号最多 14 个字符，前缀和后缀最多 13 个字符，三个字段合起来最多 14 个字符。</span><span class="sxs-lookup"><span data-stu-id="cb84a-130">The maximum number of characters is 14 for the control number, 13 for the prefix and suffix, and 14 for all three fields combined.</span></span>  
    >   
    >  <span data-ttu-id="cb84a-131">若要将组控制编号重置为指定的最小值，请单击**重置**按钮。</span><span class="sxs-lookup"><span data-stu-id="cb84a-131">To reset the group control number to the minimum value specified, click the **Reset** button.</span></span> <span data-ttu-id="cb84a-132">检查**重置为下限值超出界限时**以自动重置为最小值超过了最大值。</span><span class="sxs-lookup"><span data-stu-id="cb84a-132">Check **Reset to lower limit when out of bound** to automatically reset to the minimum value if the maximum value is exceeded.</span></span>  
  
3.  <span data-ttu-id="cb84a-133">有关**消息标头 (UNH)**，单击**应用新 ID**、 输入前缀、 参考编号范围，输入和输入 BizTalk Server 应为事务集参考编号使用的后缀。</span><span class="sxs-lookup"><span data-stu-id="cb84a-133">For **Message Header (UNH)**, click **Apply new ID**, enter the prefix, enter the reference number range, and enter the suffix that BizTalk Server should use for the transaction set reference number.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cb84a-134">第一个字段 (**UNH1.1**) 是前缀; 第二个和第三字段 (**UNH1.2**) 是参考编号范围; 和第四个字段 (**UNH1.3**) 是后缀。</span><span class="sxs-lookup"><span data-stu-id="cb84a-134">The first field (**UNH1.1**) is the prefix; the second and third fields (**UNH1.2**) are the reference number range; and the fourth field (**UNH1.3**) is the suffix.</span></span> <span data-ttu-id="cb84a-135">前缀和后缀是可选的；参考编号是必需的。</span><span class="sxs-lookup"><span data-stu-id="cb84a-135">The prefix and suffix are optional; the reference number is required.</span></span> <span data-ttu-id="cb84a-136">每条新消息的参考编号是递增的；前缀和后缀保持不变。</span><span class="sxs-lookup"><span data-stu-id="cb84a-136">The reference number is incremented for each new message; the prefix and suffix remain the same.</span></span> <span data-ttu-id="cb84a-137">参考编号的默认值范围是 1 到 99999999999999。</span><span class="sxs-lookup"><span data-stu-id="cb84a-137">The default value range for the reference number is 1 to 99999999999999.</span></span> <span data-ttu-id="cb84a-138">只允许使用数字中**UNH1.2**。</span><span class="sxs-lookup"><span data-stu-id="cb84a-138">Only numbers are allowed in **UNH1.2**.</span></span> <span data-ttu-id="cb84a-139">控制编号最多 14 个字符，前缀和后缀最多 13 个字符，三个字段合起来最多 14 个字符。</span><span class="sxs-lookup"><span data-stu-id="cb84a-139">The maximum number of characters is 14 for the control number, 13 for the prefix and suffix, and 14 for all three fields combined.</span></span>  
    >   
    >  <span data-ttu-id="cb84a-140">若要重置当前事务集控制编号的最小值，请单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="cb84a-140">To reset the current transaction set control number to the minimum value, click **Reset**.</span></span> <span data-ttu-id="cb84a-141">选择**重置为下限值超出界限时**重置控制编号的最小值，如果超过了最大值。</span><span class="sxs-lookup"><span data-stu-id="cb84a-141">Select **Reset to lower limit when out of bound** to reset the control number to the minimum value if the maximum value has been exceeded.</span></span>  
  
4.  <span data-ttu-id="cb84a-142">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="cb84a-142">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb84a-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb84a-143">See Also</span></span>  
 [<span data-ttu-id="cb84a-144">为交换处理配置 EDIFACT 后备协议属性</span><span class="sxs-lookup"><span data-stu-id="cb84a-144">Configuring EDIFACT Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)