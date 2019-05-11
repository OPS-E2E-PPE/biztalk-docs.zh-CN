---
title: 配置信封 （EDIFACT-事务集设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ec140def-6155-4b8a-8489-6e0a530bd697
caps.latest.revision: 25
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c62b963042c7a4f5ea141dd44faa4f914c30f22
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391299"
---
# <a name="configuring-envelopes-edifact-transaction-set-settings"></a><span data-ttu-id="0f2a2-102">配置信封（EDIFACT--事务集设置）</span><span class="sxs-lookup"><span data-stu-id="0f2a2-102">Configuring Envelopes (EDIFACT-Transaction Set Settings)</span></span>
<span data-ttu-id="0f2a2-103">在中**信封**页**事务集设置**部分中，可以定义 BizTalk Server 如何生成它发送到参与方的 EDIFACT 编码交换的 UNG 和 UNH 段。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-103">In the **Envelopes** page of the **Transaction Set Settings** section, you define how BizTalk Server generates the UNG and UNH segments for an EDIFACT-encoded interchange that it sends to the party.</span></span>  
  
 <span data-ttu-id="0f2a2-104">UNG 段是标识和指定的 EDIFACT 编码交换的功能组标头。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-104">The UNG segment is the header that identifies and specifies a functional group of an EDIFACT-encoded interchange.</span></span> <span data-ttu-id="0f2a2-105">它包含有关日期和时间功能组已准备好的以及类型和版本功能组中的文档的信息。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-105">It contains information about the date and time that the functional group was prepared, together with the type and version of the document in the functional group.</span></span>  
  
 <span data-ttu-id="0f2a2-106">UNH 段是交换的 EDIFACT 编码的消息标头段。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-106">The UNH segment is the message header segment of an EDIFACT-encoded interchange.</span></span> <span data-ttu-id="0f2a2-107">它提供有关消息类型，以及负责维护消息类型的发布的机构的信息。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-107">It provides information about the message type, and the agency responsible for maintaining the publication of the message type.</span></span> <span data-ttu-id="0f2a2-108">此段指示交换和文档后面的类型中的文档的开头。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-108">This segment indicates the start of a document in an interchange and the type of document that follows.</span></span>  
  
 <span data-ttu-id="0f2a2-109">在中**功能组标头 (UNG)** 部分中，你将关联**UNG**值替换**UNH**值和命名空间。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-109">In the **Functional group header (UNG)** section, you associate **UNG** values with **UNH** values and a namespace.</span></span> <span data-ttu-id="0f2a2-110">BizTalk Server 确定某一 BizTalk XML 消息已设置的值**UNH**元素并**目标命名空间**网格的行，在 BizTalk Server 将填充**UNG**网格的同一行中的值的数据元素。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-110">When BizTalk Server determines that a BizTalk XML message has the values set for the **UNH** elements and the **Target namespace** in a row of the grid, BizTalk Server will populate the **UNG** data elements with the values from the same row of the grid.</span></span> <span data-ttu-id="0f2a2-111">值**UNH**元素并**目标命名空间**必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-111">The values of the **UNH** elements and the **Target namespace** must be unique.</span></span>  
  
 <span data-ttu-id="0f2a2-112">如果消息没有与匹配**UNH**元素并**目标命名空间**BizTalk Server 将在任何行中填充该消息的值**UNG**默认行中的元素。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-112">If a message does not have a match with the **UNH** elements and the **Target namespace** in any row, BizTalk Server will populate the message with the values of the **UNG** elements in the default row.</span></span> <span data-ttu-id="0f2a2-113">将使用这些值，即使该消息没有与匹配**UNH**元素并**目标命名空间**默认行。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-113">These values will be used even if the message does not have a match with the **UNH** elements and the **Target namespace** of the default row.</span></span>  
  
 <span data-ttu-id="0f2a2-114">在 BizTalk 引擎确定某一 BizTalk XML 消息具有为 UNH 元素和目标命名空间设置的值，引擎将在网格中，提供为其设置的值填充消息中的 UNG 元素**创建分组段**选中复选框。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-114">When the BizTalk engine determines that a BizTalk XML message has the values set for the UNH elements and the Target namespace, the engine will populate the UNG elements in the message with the values set for them in the grid, provided the **Create Grouping Segments** checkbox is checked.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f2a2-115">在中**功能组标头 (UNG)** 部分中，如果您在网格中，输入设置的任何字段，然后再删除该设置，必须删除整行或该页的验证将失败。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-115">In the **Functional group header (UNG)**  section, if you enter a setting for any of the fields in the grid, and then delete that setting, you will have to delete the entire row or the page will fail validation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0f2a2-116">所有属性上将都禁用**参与方 A-> 参与方 B**单向协议选项卡，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**检查参与方 a 的框但是，所有属性都在同一页面上将都启用**参与方 B-> 参与方 A**选项卡上，如果您创建参与方 A.时选中复选框</span><span class="sxs-lookup"><span data-stu-id="0f2a2-116">All properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are enabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="0f2a2-117">先决条件</span><span class="sxs-lookup"><span data-stu-id="0f2a2-117">Prerequisites</span></span>  
 <span data-ttu-id="0f2a2-118">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-118">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-ung-and-unh-segments"></a><span data-ttu-id="0f2a2-119">定义 UNG 和 UNH 段</span><span class="sxs-lookup"><span data-stu-id="0f2a2-119">To define the UNG and UNH segments</span></span>  
  
1.  <span data-ttu-id="0f2a2-120">创建 EDIFACT 编码协议，如中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-120">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="0f2a2-121">若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-121">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="0f2a2-122">在单向协议选项卡下**事务集设置**部分中，单击**信封**。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-122">On a one-way agreement tab, under **Transaction Set Settings** section, click **Envelopes**.</span></span>  
  
3.  <span data-ttu-id="0f2a2-123">在网格的行中，输入以下值：</span><span class="sxs-lookup"><span data-stu-id="0f2a2-123">In a row of the grid, enter the following values:</span></span>  
  
    -   <span data-ttu-id="0f2a2-124">在中**对于消息类型 UNH2.1**列中，输入事务集类型。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-124">In the **For message type UNH2.1** column, enter a transaction set type.</span></span> <span data-ttu-id="0f2a2-125">（最多六个字符）。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-125">(Maximum, six characters).</span></span>  
  
    -   <span data-ttu-id="0f2a2-126">在中**UNH2.2**列中，输入消息版本号。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-126">In the **UNH2.2**  column, enter the message version number.</span></span> <span data-ttu-id="0f2a2-127">（最小值、 一个字符; 最多三个字符）。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-127">(Minimum, one character; maximum, three characters).</span></span>  
  
    -   <span data-ttu-id="0f2a2-128">在中**UNH2.3**列中，输入消息发行版号。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-128">In the **UNH2.3** column, enter the message release number.</span></span> <span data-ttu-id="0f2a2-129">（最小值、 一个字符; 最多三个字符）。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-129">(Minimum, one character; maximum, three characters).</span></span>  
  
    -   <span data-ttu-id="0f2a2-130">在中**UNH2.5**列中，输入分配的代码。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-130">In the **UNH2.5** column, enter the assigned code.</span></span> <span data-ttu-id="0f2a2-131">（最多六个字符。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-131">(Maximum, six characters.</span></span> <span data-ttu-id="0f2a2-132">必须为字母数字）。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-132">Must be alphanumeric).</span></span>  
  
    -   <span data-ttu-id="0f2a2-133">在中**目标命名空间**列中，选择架构的目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-133">In the **Target namespace** column, select the target namespace of the schema.</span></span> <span data-ttu-id="0f2a2-134">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-134">This is a required field.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0f2a2-135">这些将是 BizTalk Server 将与生成的交换关联的值进行比较的值。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-135">These will be the values that BizTalk Server will compare with the values associated with the interchange it is building.</span></span>  
  
4.  <span data-ttu-id="0f2a2-136">在网格的同一行中，输入以下值：</span><span class="sxs-lookup"><span data-stu-id="0f2a2-136">In the same row of the grid, enter the following values:</span></span>  
  
    -   <span data-ttu-id="0f2a2-137">有关**UNG1** （功能组标识） 输入包含最少一个字符，最多为 6 个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-137">For the **UNG1** (Functional group identification), enter an alphanumeric value with a minimum of one character and a maximum of six characters.</span></span> <span data-ttu-id="0f2a2-138">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-138">This is a required field.</span></span>  
  
    -   <span data-ttu-id="0f2a2-139">有关**UNG2.1** （应用程序发送方标识） 输入包含最少一个字符，最多为 35 个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-139">For **UNG2.1** (Application sender identification), enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="0f2a2-140">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-140">This is a required field.</span></span>  
  
    -   <span data-ttu-id="0f2a2-141">有关**UNG2.2** （应用程序发送方代码限定符） 输入包含最多四个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-141">For **UNG2.2** (Application sender code qualifier), enter an alphanumeric value, with a maximum of four characters.</span></span> <span data-ttu-id="0f2a2-142">这是一个可选字段。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-142">This is an optional field.</span></span>  
  
    -   <span data-ttu-id="0f2a2-143">有关**UNG3.1** （应用程序收件人标识），输入包含最少一个字符，最多为 35 个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-143">For **UNG3.1** (Application recipient identification), enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="0f2a2-144">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-144">This is a required field.</span></span>  
  
    -   <span data-ttu-id="0f2a2-145">有关**UNG3.2** （应用程序接收方代码限定符） 输入包含最多四个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-145">For **UNG3.2** (Application recipient code qualifier), enter an alphanumeric value, with a maximum of four characters.</span></span> <span data-ttu-id="0f2a2-146">这是一个可选字段。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-146">This is an optional field.</span></span>  
  
    -   <span data-ttu-id="0f2a2-147">有关**UNG6** （控制代理） 输入包含最少一个、 两个最多的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-147">For **UNG6** (Controlling agency), enter an alphanumeric value with a minimum of one and a maximum of two.</span></span> <span data-ttu-id="0f2a2-148">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-148">This is a required field.</span></span>  
  
    -   <span data-ttu-id="0f2a2-149">有关**UNG7.1** （消息类型版本号），输入包含最少一个字符，最多包含三个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-149">For **UNG7.1** (Message type version number), enter an alphanumeric value with a minimum of one character and a maximum of three characters.</span></span> <span data-ttu-id="0f2a2-150">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-150">This is a required field.</span></span>  
  
    -   <span data-ttu-id="0f2a2-151">有关**UNG7.2** （消息类型发行版号） 输入包含最少一个字符，最多包含三个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-151">For **UNG7.2** (Message type release number), enter an alphanumeric value with a minimum of one character and a maximum of three characters.</span></span> <span data-ttu-id="0f2a2-152">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-152">This is a required field.</span></span>  
  
    -   <span data-ttu-id="0f2a2-153">有关**UNG7.3** （协会分配代码），输入一个最少为 1 个字符，最多为 6 个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-153">For **UNG7.3** (Association assigned code), enter an alphanumeric value with a minimum of 1 character and a maximum of 6 characters.</span></span> <span data-ttu-id="0f2a2-154">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-154">This is a required field.</span></span>  
  
    -   <span data-ttu-id="0f2a2-155">有关**UNG8** （应用程序密码），输入包含最少一个字符，最多为 14 个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-155">For **UNG8** (Application password), enter an alphanumeric value with a minimum of one character and a maximum of 14 characters.</span></span> <span data-ttu-id="0f2a2-156">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-156">This is a required field.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0f2a2-157">这些将是 BizTalk Server 将在生成如果该交换的 UNG 字段中输入的值**对于消息类型 UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**，并**目标命名空间**同一行中的元素是那些与交换关联的匹配项。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-157">These will be the values that BizTalk Server will enter in the UNG fields of the interchange it is building if the  **For message type UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, and **Target namespace** elements in the same row are a match for those associated with the interchange.</span></span>  
  
5.  <span data-ttu-id="0f2a2-158">重复步骤 4 和 5 在网格中输入其他行。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-158">Repeat steps 4 and 5 to enter additional rows into the grid.</span></span>  
  
6.  <span data-ttu-id="0f2a2-159">在网格中的一个行，请单击**默认**以将其指定为默认行。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-159">For one row in the grid, click **Default** to designate it as the default row.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0f2a2-160">如果消息没有与匹配**UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**，和**目标命名空间**在任何行，BizTalk Server 中的元素将填充该消息的值**UNG1**， **UNG2.1**， **UNG2.2**， **UNG3.1**， **UNG3.2**， **UNG6**， **UNG7.1**， **UNG7.2**， **UNG7.3**，并**UNG8**默认行中的元素。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-160">If a message does not have a match with the **UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, and **Target namespace** elements in any row, BizTalk Server will populate the message with the values for the **UNG1**, **UNG2.1**, **UNG2.2**, **UNG3.1**, **UNG3.2**, **UNG6**, **UNG7.1**, **UNG7.2**, **UNG7.3**, and **UNG8** elements in the default row.</span></span> <span data-ttu-id="0f2a2-161">将使用这些值，即使该消息没有与匹配**对于消息类型 UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**，并**目标命名空间**默认行中的元素。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-161">These values will be used even if the message does not have a match with the **For message type UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, and **Target namespace** elements of the default row.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0f2a2-162">如果选择没有默认的行，并且消息不具有的匹配项**UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**，和**目标命名空间**元素在任何行中，BizTalk 将挂起该消息。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-162">If no default row is selected, and the message does not have a match for the **UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, and **Target namespace** elements in any row, BizTalk will suspend the message.</span></span>  
  
7.  <span data-ttu-id="0f2a2-163">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="0f2a2-163">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f2a2-164">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f2a2-164">See Also</span></span>  
 [<span data-ttu-id="0f2a2-165">配置事务集设置 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="0f2a2-165">Configuring Transaction Set Settings (EDIFACT)</span></span>](../core/configuring-transaction-set-settings-edifact.md)