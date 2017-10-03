---
title: "配置信封 （EDIFACT 事务集设置） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec140def-6155-4b8a-8489-6e0a530bd697
caps.latest.revision: "25"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a1d910f52d9ea90ae0c486356a7ecb3b01bf07a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-envelopes-edifact-transaction-set-settings"></a><span data-ttu-id="003de-102">配置信封（EDIFACT--事务集设置）</span><span class="sxs-lookup"><span data-stu-id="003de-102">Configuring Envelopes (EDIFACT-Transaction Set Settings)</span></span>
<span data-ttu-id="003de-103">在**包络线**页**事务设置设置**部分中，你定义如何 BizTalk Server 生成的 UNG 段和新罕布什尔大学段它将发送到方的 EDIFACT 编码交换。</span><span class="sxs-lookup"><span data-stu-id="003de-103">In the **Envelopes** page of the **Transaction Set Settings** section, you define how BizTalk Server generates the UNG and UNH segments for an EDIFACT-encoded interchange that it sends to the party.</span></span>  
  
 <span data-ttu-id="003de-104">UNG 段是用来标识和指定 EDIFACT 编码交换的功能组的标头。</span><span class="sxs-lookup"><span data-stu-id="003de-104">The UNG segment is the header that identifies and specifies a functional group of an EDIFACT-encoded interchange.</span></span> <span data-ttu-id="003de-105">它包含有关准备功能组的日期和时间以及功能组中文档的类型和版本的信息。</span><span class="sxs-lookup"><span data-stu-id="003de-105">It contains information about the date and time that the functional group was prepared, together with the type and version of the document in the functional group.</span></span>  
  
 <span data-ttu-id="003de-106">UNH 段是 EDIFACT 编码的交换的消息标头段。</span><span class="sxs-lookup"><span data-stu-id="003de-106">The UNH segment is the message header segment of an EDIFACT-encoded interchange.</span></span> <span data-ttu-id="003de-107">UNH 段提供了有关消息类型以及负责维护该消息类型发布的机构的信息。</span><span class="sxs-lookup"><span data-stu-id="003de-107">It provides information about the message type, and the agency responsible for maintaining the publication of the message type.</span></span> <span data-ttu-id="003de-108">该段指示交换中文档的开头以及后面文档的类型。</span><span class="sxs-lookup"><span data-stu-id="003de-108">This segment indicates the start of a document in an interchange and the type of document that follows.</span></span>  
  
 <span data-ttu-id="003de-109">在**功能组标头 (UNG)**部分中，你将关联**UNG**值与**新罕布什尔大学**值和命名空间。</span><span class="sxs-lookup"><span data-stu-id="003de-109">In the **Functional group header (UNG)** section, you associate **UNG** values with **UNH** values and a namespace.</span></span> <span data-ttu-id="003de-110">BizTalk Server 确定 BizTalk XML 消息已设置的值**新罕布什尔大学**元素和**目标命名空间**在网格的行中，BizTalk 服务器将填充**UNG**同一行的网格中的值的数据元素。</span><span class="sxs-lookup"><span data-stu-id="003de-110">When BizTalk Server determines that a BizTalk XML message has the values set for the **UNH** elements and the **Target namespace** in a row of the grid, BizTalk Server will populate the **UNG** data elements with the values from the same row of the grid.</span></span> <span data-ttu-id="003de-111">值**新罕布什尔大学**元素和**目标命名空间**必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="003de-111">The values of the **UNH** elements and the **Target namespace** must be unique.</span></span>  
  
 <span data-ttu-id="003de-112">如果消息没有包含的匹配项**新罕布什尔大学**元素和**目标命名空间**在任何行中，BizTalk Server 将填充的值的消息**UNG**默认行中的元素。</span><span class="sxs-lookup"><span data-stu-id="003de-112">If a message does not have a match with the **UNH** elements and the **Target namespace** in any row, BizTalk Server will populate the message with the values of the **UNG** elements in the default row.</span></span> <span data-ttu-id="003de-113">将使用这些值，即使消息不具有与匹配**新罕布什尔大学**元素和**目标命名空间**的默认行。</span><span class="sxs-lookup"><span data-stu-id="003de-113">These values will be used even if the message does not have a match with the **UNH** elements and the **Target namespace** of the default row.</span></span>  
  
 <span data-ttu-id="003de-114">当 BizTalk 引擎确定 BizTalk XML 消息具有新罕布什尔大学元素和目标命名空间设置的值时，引擎会使用为其设置在网格中，提供的值填充 UNG 元素在消息中的**创建分组段**选中复选框。</span><span class="sxs-lookup"><span data-stu-id="003de-114">When the BizTalk engine determines that a BizTalk XML message has the values set for the UNH elements and the Target namespace, the engine will populate the UNG elements in the message with the values set for them in the grid, provided the **Create Grouping Segments** checkbox is checked.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="003de-115">在**功能组标头 (UNG)**部分中，如果你在网格中，输入的任何字段的设置，然后删除该设置，您将需要删除整行或页将未通过验证。</span><span class="sxs-lookup"><span data-stu-id="003de-115">In the **Functional group header (UNG)**  section, if you enter a setting for any of the fields in the grid, and then delete that setting, you will have to delete the entire row or the page will fail validation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="003de-116">所有属性上将都禁用**A 方-> 方 B**单向协议选项卡，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**检查框 a 方。但是，在中相同页面上启用的所有属性**B 方-> A 方**选项卡上，如果创建 a 方。 时选中复选框</span><span class="sxs-lookup"><span data-stu-id="003de-116">All properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are enabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="003de-117">先决条件</span><span class="sxs-lookup"><span data-stu-id="003de-117">Prerequisites</span></span>  
 <span data-ttu-id="003de-118">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="003de-118">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-ung-and-unh-segments"></a><span data-ttu-id="003de-119">若要定义的段 UNG 和新罕布什尔大学段</span><span class="sxs-lookup"><span data-stu-id="003de-119">To define the UNG and UNH segments</span></span>  
  
1.  <span data-ttu-id="003de-120">创建 EDIFACT 编码协议中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。</span><span class="sxs-lookup"><span data-stu-id="003de-120">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="003de-121">若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="003de-121">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="003de-122">单向协议选项卡上，在**事务设置设置**部分中，单击**包络线**。</span><span class="sxs-lookup"><span data-stu-id="003de-122">On a one-way agreement tab, under **Transaction Set Settings** section, click **Envelopes**.</span></span>  
  
3.  <span data-ttu-id="003de-123">在网格的某行中，输入以下值：</span><span class="sxs-lookup"><span data-stu-id="003de-123">In a row of the grid, enter the following values:</span></span>  
  
    -   <span data-ttu-id="003de-124">在**消息键入 UNH2.1**列中，输入事务集类型。</span><span class="sxs-lookup"><span data-stu-id="003de-124">In the **For message type UNH2.1** column, enter a transaction set type.</span></span> <span data-ttu-id="003de-125">（最长不得超过 6 个字符）。</span><span class="sxs-lookup"><span data-stu-id="003de-125">(Maximum, six characters).</span></span>  
  
    -   <span data-ttu-id="003de-126">在**UNH2.2**列中，输入消息版本号。</span><span class="sxs-lookup"><span data-stu-id="003de-126">In the **UNH2.2**  column, enter the message version number.</span></span> <span data-ttu-id="003de-127">（最小长度为 1 个字符；最大长度为 3 个字符）。</span><span class="sxs-lookup"><span data-stu-id="003de-127">(Minimum, one character; maximum, three characters).</span></span>  
  
    -   <span data-ttu-id="003de-128">在**UNH2.3**列中，输入消息发行版号。</span><span class="sxs-lookup"><span data-stu-id="003de-128">In the **UNH2.3** column, enter the message release number.</span></span> <span data-ttu-id="003de-129">（最小长度为 1 个字符；最大长度为 3 个字符）。</span><span class="sxs-lookup"><span data-stu-id="003de-129">(Minimum, one character; maximum, three characters).</span></span>  
  
    -   <span data-ttu-id="003de-130">在**UNH2.5**列中，输入所分配的代码。</span><span class="sxs-lookup"><span data-stu-id="003de-130">In the **UNH2.5** column, enter the assigned code.</span></span> <span data-ttu-id="003de-131">（最长不得超过 6 个字符。</span><span class="sxs-lookup"><span data-stu-id="003de-131">(Maximum, six characters.</span></span> <span data-ttu-id="003de-132">必须为字母数字值）。</span><span class="sxs-lookup"><span data-stu-id="003de-132">Must be alphanumeric).</span></span>  
  
    -   <span data-ttu-id="003de-133">在**目标命名空间**列中，选择架构的目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="003de-133">In the **Target namespace** column, select the target namespace of the schema.</span></span> <span data-ttu-id="003de-134">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="003de-134">This is a required field.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="003de-135">BizTalk Server 会将这些值与它所生成的交换的关联值进行比较。</span><span class="sxs-lookup"><span data-stu-id="003de-135">These will be the values that BizTalk Server will compare with the values associated with the interchange it is building.</span></span>  
  
4.  <span data-ttu-id="003de-136">在网格的同一行中，输入以下值：</span><span class="sxs-lookup"><span data-stu-id="003de-136">In the same row of the grid, enter the following values:</span></span>  
  
    -   <span data-ttu-id="003de-137">有关**UNG1** （功能组标识），输入一个字母数字值，该值最少包含一个字符，最多六个字符。</span><span class="sxs-lookup"><span data-stu-id="003de-137">For the **UNG1** (Functional group identification), enter an alphanumeric value with a minimum of one character and a maximum of six characters.</span></span> <span data-ttu-id="003de-138">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="003de-138">This is a required field.</span></span>  
  
    -   <span data-ttu-id="003de-139">有关**UNG2.1** （应用程序发件人标识），输入一个字母数字值，该值最少包含一个字符，最多 35 个字符。</span><span class="sxs-lookup"><span data-stu-id="003de-139">For **UNG2.1** (Application sender identification), enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="003de-140">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="003de-140">This is a required field.</span></span>  
  
    -   <span data-ttu-id="003de-141">有关**UNG2.2** （应用程序发件人代码限定符），输入一个字母数字值，最多四个字符。</span><span class="sxs-lookup"><span data-stu-id="003de-141">For **UNG2.2** (Application sender code qualifier), enter an alphanumeric value, with a maximum of four characters.</span></span> <span data-ttu-id="003de-142">此字段为可选字段。</span><span class="sxs-lookup"><span data-stu-id="003de-142">This is an optional field.</span></span>  
  
    -   <span data-ttu-id="003de-143">有关**UNG3.1** （应用程序收件人标识），输入一个字母数字值，该值最少包含一个字符，最多 35 个字符。</span><span class="sxs-lookup"><span data-stu-id="003de-143">For **UNG3.1** (Application recipient identification), enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="003de-144">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="003de-144">This is a required field.</span></span>  
  
    -   <span data-ttu-id="003de-145">有关**UNG3.2** （应用程序收件人代码限定符），输入一个字母数字值，最多四个字符。</span><span class="sxs-lookup"><span data-stu-id="003de-145">For **UNG3.2** (Application recipient code qualifier), enter an alphanumeric value, with a maximum of four characters.</span></span> <span data-ttu-id="003de-146">此字段为可选字段。</span><span class="sxs-lookup"><span data-stu-id="003de-146">This is an optional field.</span></span>  
  
    -   <span data-ttu-id="003de-147">有关**UNG6** （控制机构），输入一个最小值和最多两个字母数字值。</span><span class="sxs-lookup"><span data-stu-id="003de-147">For **UNG6** (Controlling agency), enter an alphanumeric value with a minimum of one and a maximum of two.</span></span> <span data-ttu-id="003de-148">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="003de-148">This is a required field.</span></span>  
  
    -   <span data-ttu-id="003de-149">有关**UNG7.1** （消息类型版本号），输入一个字母数字值，该值最少包含一个字符，最多三个字符。</span><span class="sxs-lookup"><span data-stu-id="003de-149">For **UNG7.1** (Message type version number), enter an alphanumeric value with a minimum of one character and a maximum of three characters.</span></span> <span data-ttu-id="003de-150">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="003de-150">This is a required field.</span></span>  
  
    -   <span data-ttu-id="003de-151">有关**UNG7.2** （消息类型发行版号），输入一个字母数字值，该值最少包含一个字符，最多三个字符。</span><span class="sxs-lookup"><span data-stu-id="003de-151">For **UNG7.2** (Message type release number), enter an alphanumeric value with a minimum of one character and a maximum of three characters.</span></span> <span data-ttu-id="003de-152">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="003de-152">This is a required field.</span></span>  
  
    -   <span data-ttu-id="003de-153">有关**UNG7.3** （关联分配代码），输入一个字母数字值，该值最少包含 1 个字符，最多 6 个字符。</span><span class="sxs-lookup"><span data-stu-id="003de-153">For **UNG7.3** (Association assigned code), enter an alphanumeric value with a minimum of 1 character and a maximum of 6 characters.</span></span> <span data-ttu-id="003de-154">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="003de-154">This is a required field.</span></span>  
  
    -   <span data-ttu-id="003de-155">有关**UNG8** （应用程序密码），输入一个字母数字值，该值最少包含一个字符，最多包含 14 个字符。</span><span class="sxs-lookup"><span data-stu-id="003de-155">For **UNG8** (Application password), enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="003de-156">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="003de-156">This is a required field.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="003de-157">这些将是 BizTalk Server 将在生成如果该交换 UNG 字段中输入的值**消息键入 UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**，和**目标命名空间**同一行中的元素是交换关联的匹配项。</span><span class="sxs-lookup"><span data-stu-id="003de-157">These will be the values that BizTalk Server will enter in the UNG fields of the interchange it is building if the  **For message type UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, and **Target namespace** elements in the same row are a match for those associated with the interchange.</span></span>  
  
5.  <span data-ttu-id="003de-158">重复步骤 4 和 5 网格中输入附加行。</span><span class="sxs-lookup"><span data-stu-id="003de-158">Repeat steps 4 and 5 to enter additional rows into the grid.</span></span>  
  
6.  <span data-ttu-id="003de-159">对于在网格中的一个行，请单击**默认**以将其指定为默认行。</span><span class="sxs-lookup"><span data-stu-id="003de-159">For one row in the grid, click **Default** to designate it as the default row.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="003de-160">如果消息没有包含的匹配项**UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**，和**目标命名空间**任何行，BizTalk Server 中的元素将填充的值的消息**UNG1**， **UNG2.1**， **UNG2.2**， **UNG3.1**， **UNG3.2**， **UNG6**， **UNG7.1**， **UNG7.2**， **UNG7.3**，和**UNG8**默认行中的元素。</span><span class="sxs-lookup"><span data-stu-id="003de-160">If a message does not have a match with the **UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, and **Target namespace** elements in any row, BizTalk Server will populate the message with the values for the **UNG1**, **UNG2.1**, **UNG2.2**, **UNG3.1**, **UNG3.2**, **UNG6**, **UNG7.1**, **UNG7.2**, **UNG7.3**, and **UNG8** elements in the default row.</span></span> <span data-ttu-id="003de-161">将使用这些值，即使消息不具有与匹配**消息键入 UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**，和**目标命名空间**默认行的元素。</span><span class="sxs-lookup"><span data-stu-id="003de-161">These values will be used even if the message does not have a match with the **For message type UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, and **Target namespace** elements of the default row.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="003de-162">如果选择没有默认行，并且邮件未包含的匹配项**UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**，和**目标命名空间**在任何行中，BizTalk 的元素将会挂起消息。</span><span class="sxs-lookup"><span data-stu-id="003de-162">If no default row is selected, and the message does not have a match for the **UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, and **Target namespace** elements in any row, BizTalk will suspend the message.</span></span>  
  
7.  <span data-ttu-id="003de-163">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="003de-163">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="003de-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="003de-164">See Also</span></span>  
 [<span data-ttu-id="003de-165">配置事务集设置 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="003de-165">Configuring Transaction Set Settings (EDIFACT)</span></span>](../core/configuring-transaction-set-settings-edifact.md)