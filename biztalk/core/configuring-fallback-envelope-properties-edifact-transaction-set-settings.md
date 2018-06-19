---
title: 配置回退信封属性 （EDIFACT 事务集设置） |Microsoft 文档
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
ms.openlocfilehash: c93f9aae6d67e5dc56d383626e36d1db412be9d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233717"
---
# <a name="configuring-fallback-envelope-properties-edifact-transaction-set-settings"></a><span data-ttu-id="8acce-102">配置回退信封属性（EDIFACT-事务集设置）</span><span class="sxs-lookup"><span data-stu-id="8acce-102">Configuring Fallback Envelope Properties (EDIFACT-Transaction Set Settings)</span></span>
<span data-ttu-id="8acce-103">在**包络线**页**事务设置设置**部分中，你定义 BizTalk Server 如何生成它将发送到方的 EDIFACT 编码交换 UNG 段。</span><span class="sxs-lookup"><span data-stu-id="8acce-103">In the **Envelopes** page of the **Transaction Set Settings** section, you define how BizTalk Server generates the UNG segments for an EDIFACT-encoded interchange that it sends to the party.</span></span>  
  
 <span data-ttu-id="8acce-104">UNG 段是用来标识和指定 EDIFACT 编码交换的功能组的标头。</span><span class="sxs-lookup"><span data-stu-id="8acce-104">The UNG segment is the header that identifies and specifies a functional group of an EDIFACT-encoded interchange.</span></span> <span data-ttu-id="8acce-105">它包含有关准备功能组的日期和时间以及功能组中文档的类型和版本的信息。</span><span class="sxs-lookup"><span data-stu-id="8acce-105">It contains information about the date and time that the functional group was prepared, together with the type and version of the document in the functional group.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8acce-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="8acce-106">Prerequisites</span></span>  
 <span data-ttu-id="8acce-107">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="8acce-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-ung-segments"></a><span data-ttu-id="8acce-108">定义 UNG 段</span><span class="sxs-lookup"><span data-stu-id="8acce-108">To define the UNG segments</span></span>  
  
1.  <span data-ttu-id="8acce-109">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 回退设置**。</span><span class="sxs-lookup"><span data-stu-id="8acce-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="8acce-110">在**EDIFACT 回退设置**对话框中，在**EDIFACT 协议页**选项卡上，在**事务设置设置**部分中，单击**包络线**.</span><span class="sxs-lookup"><span data-stu-id="8acce-110">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Transaction Set Settings** section, click **Envelopes**.</span></span>  
  
3.  <span data-ttu-id="8acce-111">有关**功能组 ID (UNG1)**，输入一个字母数字值，该值最少包含一个字符，最多六个字符。</span><span class="sxs-lookup"><span data-stu-id="8acce-111">For **Functional group ID (UNG1)**, enter an alphanumeric value with a minimum of one character and a maximum of six characters.</span></span> <span data-ttu-id="8acce-112">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="8acce-112">This is a required field.</span></span>  
  
4.  <span data-ttu-id="8acce-113">输入值以标识**应用程序发件人 (UNG2)**。</span><span class="sxs-lookup"><span data-stu-id="8acce-113">Enter values to identify **Application sender (UNG2)**.</span></span>  
  
    -   <span data-ttu-id="8acce-114">有关**标识 (UNG2.1)**，输入一个字母数字值，该值最少包含一个字符，最多 35 个字符。</span><span class="sxs-lookup"><span data-stu-id="8acce-114">For **Identification (UNG2.1)**, enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="8acce-115">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="8acce-115">This is a required field.</span></span>  
  
    -   <span data-ttu-id="8acce-116">有关**代码限定符 (UNG2.2)**，输入一个字母数字值，该值最少包含一个字符，最多四个字符。</span><span class="sxs-lookup"><span data-stu-id="8acce-116">For **Code qualifier (UNG2.2)**, enter an alphanumeric value with a minimum of one character and a maximum of four characters.</span></span> <span data-ttu-id="8acce-117">此字段为可选字段。</span><span class="sxs-lookup"><span data-stu-id="8acce-117">This is an optional field.</span></span>  
  
5.  <span data-ttu-id="8acce-118">输入值以标识**应用程序接收方 (UNG3)**。</span><span class="sxs-lookup"><span data-stu-id="8acce-118">Enter values to identify **Application recipient (UNG3)**.</span></span>  
  
    -   <span data-ttu-id="8acce-119">有关**标识 (UNG3.1)**，输入一个字母数字值，该值最少包含一个字符，最多 35 个字符。</span><span class="sxs-lookup"><span data-stu-id="8acce-119">For **Identification (UNG3.1)**, enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="8acce-120">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="8acce-120">This is a required field.</span></span>  
  
    -   <span data-ttu-id="8acce-121">有关**代码限定符 (UNG3.2)**，输入一个字母数字值，该值最少包含一个字符，最多四个字符。</span><span class="sxs-lookup"><span data-stu-id="8acce-121">For **Code qualifier (UNG3.2)**, enter an alphanumeric value with a minimum of one character and a maximum of four characters.</span></span> <span data-ttu-id="8acce-122">此字段为可选字段。</span><span class="sxs-lookup"><span data-stu-id="8acce-122">This is an optional field.</span></span>  
  
6.  <span data-ttu-id="8acce-123">有关**控制代理 (UNG6)**，输入最少包含一个字符，最多两个字符的一个字母数字值。</span><span class="sxs-lookup"><span data-stu-id="8acce-123">For **Controlling agency (UNG6)**, enter an alphanumeric value with a minimum of one character and a maximum of two characters.</span></span> <span data-ttu-id="8acce-124">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="8acce-124">This is a required field.</span></span>  
  
7.  <span data-ttu-id="8acce-125">输入值以标识**消息版本 (UNG7)**。</span><span class="sxs-lookup"><span data-stu-id="8acce-125">Enter values to identify **Message version (UNG7)**.</span></span>  
  
    -   <span data-ttu-id="8acce-126">有关**版本 (UNG7.1)**，输入一个字母数字值，该值最少包含一个字符，最多三个字符。</span><span class="sxs-lookup"><span data-stu-id="8acce-126">For **Version (UNG7.1)**, enter an alphanumeric value with a minimum of one character and a maximum of three characters.</span></span> <span data-ttu-id="8acce-127">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="8acce-127">This is a required field.</span></span>  
  
    -   <span data-ttu-id="8acce-128">有关**发行版 (UNG7.2)**，输入一个字母数字值，该值最少包含一个字符，最多三个字符。</span><span class="sxs-lookup"><span data-stu-id="8acce-128">For **Release (UNG7.2)**, enter an alphanumeric value with a minimum of one character and a maximum of three characters.</span></span> <span data-ttu-id="8acce-129">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="8acce-129">This is a required field.</span></span>  
  
    -   <span data-ttu-id="8acce-130">有关**关联分配的代码 (UNG7.3)**，输入一个字母数字值，该值最少包含 1 个字符，最多 6 个字符。</span><span class="sxs-lookup"><span data-stu-id="8acce-130">For **Association assigned code (UNG7.3)**, enter an alphanumeric value with a minimum of 1 character and a maximum of 6 characters.</span></span> <span data-ttu-id="8acce-131">此字段为可选字段。</span><span class="sxs-lookup"><span data-stu-id="8acce-131">This is an optional field.</span></span>  
  
8.  <span data-ttu-id="8acce-132">有关**应用程序密码 (UNG8)**，输入一个字母数字值，该值最少包含一个字符，最多包含 14 个字符。</span><span class="sxs-lookup"><span data-stu-id="8acce-132">For **Application password (UNG8)**, enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="8acce-133">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="8acce-133">This is a required field.</span></span>  
  
9. <span data-ttu-id="8acce-134">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="8acce-134">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8acce-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8acce-135">See Also</span></span>  
 [<span data-ttu-id="8acce-136">为事务配置 EDIFACT 回退协议属性设置</span><span class="sxs-lookup"><span data-stu-id="8acce-136">Configuring EDIFACT Fallback Agreement Properties for Transaction Set Settings</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-transaction-set-settings.md)