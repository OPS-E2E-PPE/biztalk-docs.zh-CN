---
title: 配置回退本地主机设置 （X12-交换设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b552fa2b-1154-491f-9bcf-aaba3b8f343f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57763ad613025f475ae141a884bd9994a8e8a209
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012558"
---
# <a name="configuring-fallback-local-host-settings-x12-interchange-settings"></a><span data-ttu-id="f27a2-102">配置回退本地主机设置（X12-交换设置）</span><span class="sxs-lookup"><span data-stu-id="f27a2-102">Configuring Fallback Local Host Settings (X12-Interchange Settings)</span></span>
<span data-ttu-id="f27a2-103">本地主机设置控制如何处理 EDI 交换。</span><span class="sxs-lookup"><span data-stu-id="f27a2-103">The local host settings govern how the EDI interchanges are processed.</span></span> <span data-ttu-id="f27a2-104">此页上的设置可以分为两个类别：接收方设置（用于传入交换）和发送方设置（用于传出交换）。</span><span class="sxs-lookup"><span data-stu-id="f27a2-104">The settings on this page can be divided into two categories – receiver’s settings (for incoming interchanges) and sender’s settings (for outgoing interchanges).</span></span> <span data-ttu-id="f27a2-105">作为接收方设置的一部分，可以指定生成 ST02 的方式，确认控制编号。</span><span class="sxs-lookup"><span data-stu-id="f27a2-105">As part of the receiver’s settings, you can specify how the ST02 will be generated, the acknowledgement control number.</span></span> <span data-ttu-id="f27a2-106">作为发送方设置的一部分，可以指定为传出消息生成控制编号的方式。</span><span class="sxs-lookup"><span data-stu-id="f27a2-106">As part of the sender’s settings, you can specify how the control numbers are generated for outgoing messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f27a2-107">此处所述的设置同样适用于 HIPAA 交换。</span><span class="sxs-lookup"><span data-stu-id="f27a2-107">The settings described here also apply to HIPAA interchanges.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f27a2-108">必要條件</span><span class="sxs-lookup"><span data-stu-id="f27a2-108">Prerequisites</span></span>  
 <span data-ttu-id="f27a2-109">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="f27a2-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-local-host--receivers-settings"></a><span data-ttu-id="f27a2-110">配置本地主机 – 接收方设置</span><span class="sxs-lookup"><span data-stu-id="f27a2-110">To configure local host – receiver’s settings</span></span>  
  
1. <span data-ttu-id="f27a2-111">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 后备设置**。</span><span class="sxs-lookup"><span data-stu-id="f27a2-111">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="f27a2-112">在中**X12 后备设置**对话框中**X12 协议页**选项卡上，在**交换设置**部分中，单击**本地主机设置**.</span><span class="sxs-lookup"><span data-stu-id="f27a2-112">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Interchange Settings** section, click **Local Host Settings**.</span></span>  
  
3. <span data-ttu-id="f27a2-113">若要指定确认中使用的事务集控制编号范围，请输入中的值**确认控制编号 (ST02)** 字段。</span><span class="sxs-lookup"><span data-stu-id="f27a2-113">To designate the range of transaction set control numbers used in an acknowledgment, enter values in the **ACK Control number (ST02)** fields.</span></span> <span data-ttu-id="f27a2-114">请在中间两个字段中输入一个数值，而为前缀和后缀字段输入字母数字值（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="f27a2-114">Enter a numeric value for the middle two fields, and an alphanumeric value (if desired) for the prefix and suffix fields.</span></span> <span data-ttu-id="f27a2-115">中间字段是必填字段，包含控制编号的最小值和最大值；前缀和后缀可选。</span><span class="sxs-lookup"><span data-stu-id="f27a2-115">The middle fields are required and contain the minimum and maximum values for the control number; the prefix and suffix are optional.</span></span> <span data-ttu-id="f27a2-116">所有三个字段的最大长度均为 9 个字符。</span><span class="sxs-lookup"><span data-stu-id="f27a2-116">The maximum length for all three fields is nine characters.</span></span>  
  
    <span data-ttu-id="f27a2-117">若要重置当前事务集控制编号的最小值，请单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="f27a2-117">To reset the current transaction set control number to the minimum value, click **Reset**.</span></span> <span data-ttu-id="f27a2-118">检查**重置为下限值超出界限时**重置为下限的控制编号，一旦超出了最大值。</span><span class="sxs-lookup"><span data-stu-id="f27a2-118">Check **Reset to lower limit when out of bound** to reset the control number to the lower limit once the maximum value has been exceeded.</span></span>  
  
### <a name="to-configure-local-host--senders-settings"></a><span data-ttu-id="f27a2-119">配置本地主机 – 发送方设置</span><span class="sxs-lookup"><span data-stu-id="f27a2-119">To configure local host – sender’s settings</span></span>  
  
1.  <span data-ttu-id="f27a2-120">有关**交换控制编号 (ISA13)**，输入要由 BizTalk Server 生成传出交换的交换控制编号的值的范围。</span><span class="sxs-lookup"><span data-stu-id="f27a2-120">For **Interchange control number (ISA13)**, enter a range of values for the interchange control number to be used by BizTalk Server in generating an outgoing interchange.</span></span> <span data-ttu-id="f27a2-121">输入一个最小为 1、最大为 999999999 的数值。</span><span class="sxs-lookup"><span data-stu-id="f27a2-121">Enter a numeric value with a minimum of 1 and a maximum of 999999999.</span></span> <span data-ttu-id="f27a2-122">此字段是必需字段。</span><span class="sxs-lookup"><span data-stu-id="f27a2-122">This is a mandatory field.</span></span>  
  
     <span data-ttu-id="f27a2-123">若要将控制编号重置为指定的最小值，请单击**重置**按钮。</span><span class="sxs-lookup"><span data-stu-id="f27a2-123">To reset the control number to the minimum value specified, click the **Reset** button.</span></span> <span data-ttu-id="f27a2-124">检查**重置为下限值超出界限时**以自动重置为最小值超过了最大值。</span><span class="sxs-lookup"><span data-stu-id="f27a2-124">Check **Reset to lower limit when out of bound** to automatically reset to the minimum value if the maximum value is exceeded.</span></span>  
  
2.  <span data-ttu-id="f27a2-125">有关**组控制编号 (GS06)**，输入 BizTalk Server 应为组控制编号使用的数字范围。</span><span class="sxs-lookup"><span data-stu-id="f27a2-125">For **Group control number (GS06)**, enter the range of numbers that BizTalk Server should use for the group control number.</span></span> <span data-ttu-id="f27a2-126">输入一个最小为 1 个字符最大为 9 个字符的数值。</span><span class="sxs-lookup"><span data-stu-id="f27a2-126">Enter a numeric value with a minimum of one character and a maximum of nine characters.</span></span> <span data-ttu-id="f27a2-127">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="f27a2-127">This is a required field.</span></span>  
  
     <span data-ttu-id="f27a2-128">若要将组控制编号重置为指定的最小值，请单击**重置**按钮。</span><span class="sxs-lookup"><span data-stu-id="f27a2-128">To reset the group control number to the minimum value specified, click the **Reset** button.</span></span> <span data-ttu-id="f27a2-129">检查**重置为下限值超出界限时**以自动重置为最小值超过了最大值。</span><span class="sxs-lookup"><span data-stu-id="f27a2-129">Check **Reset to lower limit when out of bound** to automatically reset to the minimum value if the maximum value is exceeded.</span></span>  
  
3.  <span data-ttu-id="f27a2-130">有关**事务集控制编号 (ST02)**，单击**应用新 ID**，然后为可选前缀和后缀输入所需的中间字段的数值和字母数字值的范围。</span><span class="sxs-lookup"><span data-stu-id="f27a2-130">For **Transaction Set Control number (ST02)**, click **Apply new ID**, and then enter a range of numeric values for the required middle fields, and alphanumeric values for the optional prefix and suffix.</span></span> <span data-ttu-id="f27a2-131">所有四个字段的最大长度为 9 个字符。</span><span class="sxs-lookup"><span data-stu-id="f27a2-131">The maximum length of all four fields is nine characters.</span></span>  
  
     <span data-ttu-id="f27a2-132">若要重置当前事务集控制编号的最小值，请单击**重置**。</span><span class="sxs-lookup"><span data-stu-id="f27a2-132">To reset the current transaction set control number to the minimum value, click **Reset**.</span></span> <span data-ttu-id="f27a2-133">选择**重置为下限值超出界限时**重置控制编号的最小值，如果超过了最大值。</span><span class="sxs-lookup"><span data-stu-id="f27a2-133">Select **Reset to lower limit when out of bound** to reset the control number to the minimum value if the maximum value has been exceeded.</span></span>  
  
4.  <span data-ttu-id="f27a2-134">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="f27a2-134">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f27a2-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="f27a2-135">See Also</span></span>  
 [<span data-ttu-id="f27a2-136">为交换处理配置 X12 后备协议属性</span><span class="sxs-lookup"><span data-stu-id="f27a2-136">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)