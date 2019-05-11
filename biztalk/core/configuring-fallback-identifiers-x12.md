---
title: 配置回退标识符 (X12) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2cb5b32c-96ec-4192-9a10-6668a2cb1195
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d5612b0b6ffafd52709710148ee62d06245fb191
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391233"
---
# <a name="configuring-fallback-identifiers-x12"></a><span data-ttu-id="4c467-102">配置回退标识符(X12)</span><span class="sxs-lookup"><span data-stu-id="4c467-102">Configuring Fallback Identifiers (X12)</span></span>
<span data-ttu-id="4c467-103">在后备协议中，你必须设置 X12 授权和安全属性，以确认交换不被通过接收未经授权的收件人。</span><span class="sxs-lookup"><span data-stu-id="4c467-103">In the fallback agreement, you must set the X12 authorization and security properties in order to verify that the interchange is not being received by unauthorized recipients.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c467-104">此处所述的交换处理属性也适用于 HIPAA 交换。</span><span class="sxs-lookup"><span data-stu-id="4c467-104">The interchange processing properties described here apply also to HIPAA interchanges.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4c467-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="4c467-105">Prerequisites</span></span>  
 <span data-ttu-id="4c467-106">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="4c467-106">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-set-sender-receiver-and-security-properties"></a><span data-ttu-id="4c467-107">若要设置发件人、 接收器和安全属性</span><span class="sxs-lookup"><span data-stu-id="4c467-107">To set sender, receiver, and security properties</span></span>  
  
1. <span data-ttu-id="4c467-108">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 后备设置**。</span><span class="sxs-lookup"><span data-stu-id="4c467-108">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="4c467-109">在中**X12 后备设置**对话框中**X12 协议页**选项卡上，在**交换设置**部分中，单击**标识符**.</span><span class="sxs-lookup"><span data-stu-id="4c467-109">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Interchange Settings** section, click **Identifiers**.</span></span>  
  
3. <span data-ttu-id="4c467-110">输入值**ISA1-2 （授权限定符和信息）**。</span><span class="sxs-lookup"><span data-stu-id="4c467-110">Enter values for the **ISA1-2 (Authorization qualifier and information)**.</span></span> <span data-ttu-id="4c467-111">选择的值**授权限定符 (ISA1)** 从关联的下拉列表。</span><span class="sxs-lookup"><span data-stu-id="4c467-111">Select the value for the **Authorization qualifier (ISA1)** from the associated drop-down list.</span></span> <span data-ttu-id="4c467-112">如果此值不是**00**，对于**值 (ISA2)** 文字框中，输入一个字母数字字符的最小值和最多 10 个。</span><span class="sxs-lookup"><span data-stu-id="4c467-112">If this value is other than **00**, for the **Value (ISA2)** text box, enter a minimum of one alphanumeric character and a maximum of 10.</span></span> <span data-ttu-id="4c467-113">这是一个可选字段。</span><span class="sxs-lookup"><span data-stu-id="4c467-113">This is an optional field.</span></span> <span data-ttu-id="4c467-114">如果您指定这些值，请确保它们匹配接收交换中的 ISA1 和 ISA2 字段否则[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将挂起该交换。</span><span class="sxs-lookup"><span data-stu-id="4c467-114">If you do specify these values, make sure they match the ISA1 and ISA2 fields in a received interchange otherwise [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will suspend the interchange.</span></span>  
  
4. <span data-ttu-id="4c467-115">输入值**ISA3-4 （安全限定符和信息）**。</span><span class="sxs-lookup"><span data-stu-id="4c467-115">Enter values for the **ISA3-4 (Security qualifier and information)**.</span></span> <span data-ttu-id="4c467-116">选择的值**安全限定符 (ISA3)** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="4c467-116">Select the value for the **Security qualifier (ISA3)** from the drop-down list.</span></span> <span data-ttu-id="4c467-117">如果此值不是**00**，对于**值 (ISA4)** 文字框中，输入一个字母数字值的最小值和最多 10 个。</span><span class="sxs-lookup"><span data-stu-id="4c467-117">If this value is other than **00**, for the **Value (ISA4)** text box, enter a minimum of one alphanumeric value and a maximum of 10.</span></span> <span data-ttu-id="4c467-118">这是一个可选字段。</span><span class="sxs-lookup"><span data-stu-id="4c467-118">This is an optional field.</span></span> <span data-ttu-id="4c467-119">如果这些值不匹配的已接收交换中的 ISA3 和 ISA4 字段[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将挂起该交换。</span><span class="sxs-lookup"><span data-stu-id="4c467-119">If these values do not match the ISA3 and ISA4 fields in a received interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will suspend the interchange.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4c467-120">值**03 – 密码 （用于向后兼容性）**，是为了向后兼容包含[!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)]和将在未来版本中删除。</span><span class="sxs-lookup"><span data-stu-id="4c467-120">The value **03 – Password (for backward compatibility)**, is included for backward compatibility with [!INCLUDE[btsbiztalkserver2006r2](../includes/btsbiztalkserver2006r2-md.md)] and will be removed in future versions.</span></span>  
  
5. <span data-ttu-id="4c467-121">输入的值**ISA5-6 （发送方限定符和标识符）**。</span><span class="sxs-lookup"><span data-stu-id="4c467-121">Enter the values for **ISA5-6 (Sender qualifier and identifier)**.</span></span> <span data-ttu-id="4c467-122">选择从限定符的值**发件人 Id 限定符 (ISA5)** 下拉列表。</span><span class="sxs-lookup"><span data-stu-id="4c467-122">Select a value for the qualifier from the **Sender Id Qualifier (ISA5)** drop-down list.</span></span> <span data-ttu-id="4c467-123">对于标识符，在**值 (ISA6)** 文字框中，输入最少一个字母数字字符、 最多包含 15 个字符。</span><span class="sxs-lookup"><span data-stu-id="4c467-123">For the identifier, in the **Value (ISA6)** text box, enter a minimum of one alphanumeric character and a maximum of 15 characters.</span></span>  
  
6. <span data-ttu-id="4c467-124">输入的值**ISA7-8 （接收方限定符和标识符）**。</span><span class="sxs-lookup"><span data-stu-id="4c467-124">Enter the values for **ISA7-8 (Receiver qualifier and identifier)**.</span></span> <span data-ttu-id="4c467-125">选择从限定符的值**接收方 Id 限定符 (ISA7)** 下拉列表。</span><span class="sxs-lookup"><span data-stu-id="4c467-125">Select a value for the qualifier from the **Receiver Id Qualifier (ISA7)** drop-down list.</span></span> <span data-ttu-id="4c467-126">对于标识符，在**值 (ISA8)** 文字框中，输入最少一个字母数字字符、 最多包含 15 个字符。</span><span class="sxs-lookup"><span data-stu-id="4c467-126">For the identifier, in the **Value (ISA8)** text box, enter a minimum of one alphanumeric character and a maximum of 15 characters.</span></span>  
  
7. <span data-ttu-id="4c467-127">单击**Apply**以接受更改，或单击**确定**以输入和验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="4c467-127">Click **Apply** to accept the changes, or click **OK** to enter and validate the changes, and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c467-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="4c467-128">See Also</span></span>  
 [<span data-ttu-id="4c467-129">为交换处理配置 X12 后备协议属性</span><span class="sxs-lookup"><span data-stu-id="4c467-129">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)