---
title: 配置回退信封属性 （EDIFACT-事务集设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b56a5a93-35ac-4293-b00e-28dcd89dfa2a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6d0dbad19076ab457f91dc41970d1c07c88cf45e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391335"
---
# <a name="configuring-fallback-envelope-properties-edifact-transaction-set-settings"></a><span data-ttu-id="8804d-102">配置回退信封属性（EDIFACT-事务集设置）</span><span class="sxs-lookup"><span data-stu-id="8804d-102">Configuring Fallback Envelope Properties (EDIFACT-Transaction Set Settings)</span></span>
<span data-ttu-id="8804d-103">在中**信封**页**事务集设置**部分中，可以定义 BizTalk Server 如何生成它发送到参与方的 EDIFACT 编码交换的 UNG 段。</span><span class="sxs-lookup"><span data-stu-id="8804d-103">In the **Envelopes** page of the **Transaction Set Settings** section, you define how BizTalk Server generates the UNG segments for an EDIFACT-encoded interchange that it sends to the party.</span></span>  
  
 <span data-ttu-id="8804d-104">UNG 段是标识和指定的 EDIFACT 编码交换的功能组标头。</span><span class="sxs-lookup"><span data-stu-id="8804d-104">The UNG segment is the header that identifies and specifies a functional group of an EDIFACT-encoded interchange.</span></span> <span data-ttu-id="8804d-105">它包含有关日期和时间功能组已准备好的以及类型和版本功能组中的文档的信息。</span><span class="sxs-lookup"><span data-stu-id="8804d-105">It contains information about the date and time that the functional group was prepared, together with the type and version of the document in the functional group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8804d-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="8804d-106">Prerequisites</span></span>  
 <span data-ttu-id="8804d-107">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="8804d-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-ung-segments"></a><span data-ttu-id="8804d-108">定义 UNG 段</span><span class="sxs-lookup"><span data-stu-id="8804d-108">To define the UNG segments</span></span>  
  
1. <span data-ttu-id="8804d-109">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 后备设置**。</span><span class="sxs-lookup"><span data-stu-id="8804d-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="8804d-110">在中**EDIFACT 后备设置**对话框中**EDIFACT 协议页**选项卡上，在**事务集设置**部分中，单击**信封**.</span><span class="sxs-lookup"><span data-stu-id="8804d-110">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Transaction Set Settings** section, click **Envelopes**.</span></span>  
  
3. <span data-ttu-id="8804d-111">有关**的功能组 ID (UNG1)**，输入包含最少一个字符，最多为 6 个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="8804d-111">For **Functional group ID (UNG1)**, enter an alphanumeric value with a minimum of one character and a maximum of six characters.</span></span> <span data-ttu-id="8804d-112">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="8804d-112">This is a required field.</span></span>  
  
4. <span data-ttu-id="8804d-113">输入值以标识**应用程序发送方 (UNG2)**。</span><span class="sxs-lookup"><span data-stu-id="8804d-113">Enter values to identify **Application sender (UNG2)**.</span></span>  
  
   -   <span data-ttu-id="8804d-114">有关**标识 (UNG2.1)**，输入包含最少一个字符，最多为 35 个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="8804d-114">For **Identification (UNG2.1)**, enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="8804d-115">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="8804d-115">This is a required field.</span></span>  
  
   -   <span data-ttu-id="8804d-116">有关**代码限定符 (UNG2.2)**，输入包含最少一个字符，最多四个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="8804d-116">For **Code qualifier (UNG2.2)**, enter an alphanumeric value with a minimum of one character and a maximum of four characters.</span></span> <span data-ttu-id="8804d-117">这是一个可选字段。</span><span class="sxs-lookup"><span data-stu-id="8804d-117">This is an optional field.</span></span>  
  
5. <span data-ttu-id="8804d-118">输入值以标识**应用程序接收方 (UNG3)**。</span><span class="sxs-lookup"><span data-stu-id="8804d-118">Enter values to identify **Application recipient (UNG3)**.</span></span>  
  
   -   <span data-ttu-id="8804d-119">有关**标识 (UNG3.1)**，输入包含最少一个字符，最多为 35 个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="8804d-119">For **Identification (UNG3.1)**, enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="8804d-120">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="8804d-120">This is a required field.</span></span>  
  
   -   <span data-ttu-id="8804d-121">有关**代码限定符 (UNG3.2)**，输入包含最少一个字符，最多四个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="8804d-121">For **Code qualifier (UNG3.2)**, enter an alphanumeric value with a minimum of one character and a maximum of four characters.</span></span> <span data-ttu-id="8804d-122">这是一个可选字段。</span><span class="sxs-lookup"><span data-stu-id="8804d-122">This is an optional field.</span></span>  
  
6. <span data-ttu-id="8804d-123">有关**控制代理 (UNG6)**，输入包含最少一个字符，最多两个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="8804d-123">For **Controlling agency (UNG6)**, enter an alphanumeric value with a minimum of one character and a maximum of two characters.</span></span> <span data-ttu-id="8804d-124">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="8804d-124">This is a required field.</span></span>  
  
7. <span data-ttu-id="8804d-125">输入值以标识**消息版本 (UNG7)**。</span><span class="sxs-lookup"><span data-stu-id="8804d-125">Enter values to identify **Message version (UNG7)**.</span></span>  
  
   -   <span data-ttu-id="8804d-126">有关**版本 (UNG7.1)**，输入包含最少一个字符，最多包含三个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="8804d-126">For **Version (UNG7.1)**, enter an alphanumeric value with a minimum of one character and a maximum of three characters.</span></span> <span data-ttu-id="8804d-127">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="8804d-127">This is a required field.</span></span>  
  
   -   <span data-ttu-id="8804d-128">有关**版本 (UNG7.2)**，输入包含最少一个字符，最多包含三个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="8804d-128">For **Release (UNG7.2)**, enter an alphanumeric value with a minimum of one character and a maximum of three characters.</span></span> <span data-ttu-id="8804d-129">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="8804d-129">This is a required field.</span></span>  
  
   -   <span data-ttu-id="8804d-130">有关**协会分配代码 (UNG7.3)**，输入一个最少为 1 个字符，最多为 6 个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="8804d-130">For **Association assigned code (UNG7.3)**, enter an alphanumeric value with a minimum of 1 character and a maximum of 6 characters.</span></span> <span data-ttu-id="8804d-131">这是一个可选字段。</span><span class="sxs-lookup"><span data-stu-id="8804d-131">This is an optional field.</span></span>  
  
8. <span data-ttu-id="8804d-132">有关**应用程序密码 (UNG8)**，输入包含最少一个字符，最多为 14 个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="8804d-132">For **Application password (UNG8)**, enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="8804d-133">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="8804d-133">This is a required field.</span></span>  
  
9. <span data-ttu-id="8804d-134">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="8804d-134">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8804d-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="8804d-135">See Also</span></span>  
 [<span data-ttu-id="8804d-136">为事务集设置配置 EDIFACT 后备协议属性</span><span class="sxs-lookup"><span data-stu-id="8804d-136">Configuring EDIFACT Fallback Agreement Properties for Transaction Set Settings</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-transaction-set-settings.md)