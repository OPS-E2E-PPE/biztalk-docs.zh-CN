---
title: 配置信封 （X12-事务集设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9313a7b9-72fa-4071-8c65-007371643179
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b478f566301e01fa26d1d72e8eadf80caafa9e7d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65391271"
---
# <a name="configuring-envelopes-x12-transaction-set-settings"></a><span data-ttu-id="f7128-102">配置信封（X12--事务集设置）</span><span class="sxs-lookup"><span data-stu-id="f7128-102">Configuring Envelopes (X12-Transaction Set Settings)</span></span>
<span data-ttu-id="f7128-103">在中**信封**页**事务集设置**部分中，可以定义 BizTalk Server 如何生成它发送到参与方的 X12 编码交换的 GS 和 ST 段。</span><span class="sxs-lookup"><span data-stu-id="f7128-103">In the **Envelops** page of the **Transaction Set Settings** section, you define how BizTalk Server generates the GS and ST segments for an X12-encoded interchange that it sends to the party.</span></span> <span data-ttu-id="f7128-104">GS 段标识，并指定功能组对于 X12 编码的交换。</span><span class="sxs-lookup"><span data-stu-id="f7128-104">A GS segment identifies and specifies a functional group for an X12-encoded interchange.</span></span> <span data-ttu-id="f7128-105">ST 段是 X12 编码交换的消息标头。</span><span class="sxs-lookup"><span data-stu-id="f7128-105">An ST segment is the message header for an X12-encoded interchange.</span></span>  
  
 <span data-ttu-id="f7128-106">在此页上，将关联的值**GS1**， **GS2**， **GS3**， **GS4**， **GS5**， **GS7**，并**GS8**值的数据元素**事务类型**，**版本/发行版**，和**目标命名空间**数据元素。</span><span class="sxs-lookup"><span data-stu-id="f7128-106">In this page, you associate values of the **GS1**, **GS2**, **GS3**, **GS4**, **GS5**, **GS7**, and **GS8** data elements with values of the **Transaction Type**, **Version/Release**, and **Target namespace** data elements.</span></span> <span data-ttu-id="f7128-107">当 BizTalk 确定某一 BizTalk XML 消息已设置的值**事务类型**，**版本/发行版**，并**目标命名空间**网格中的某一行中的元素BizTalk 将填充**GS1**， **GS2**， **GS3**， **GS4**， **GS5**， **GS7**，并**GS8**传出的信封中的数据元素交换网格的同一行中的值。</span><span class="sxs-lookup"><span data-stu-id="f7128-107">When BizTalk determines that a BizTalk XML message has the values set for the **Transaction Type**, **Version/Release**, and **Target namespace** elements in a row of the grid, BizTalk will populate the **GS1**, **GS2**, **GS3**, **GS4**, **GS5**, **GS7**, and **GS8** data elements in the envelope of the outgoing interchange with the values from the same row of the grid.</span></span> <span data-ttu-id="f7128-108">值**事务类型**，**版本/发行版**，并**目标命名空间**元素必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="f7128-108">The values of the **Transaction Type**, **Version/Release**, and **Target namespace** elements must be unique.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7128-109">如果您在网格中，输入设置的任何字段，然后删除该设置，必须删除整行或该页的验证将失败。</span><span class="sxs-lookup"><span data-stu-id="f7128-109">If you enter a setting for any of the fields in the grid, and then delete that setting, you will have to delete the entire row or the page will fail validation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7128-110">本主题还适用于与 HIPAA 相关的设置。</span><span class="sxs-lookup"><span data-stu-id="f7128-110">This topic applies also to HIPAA-related settings.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f7128-111">所有属性上将都禁用**参与方 A-> 参与方 B**单向协议选项卡，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**检查参与方 a 的框但是，所有属性都在同一页面上将都启用**参与方 B-> 参与方 A**选项卡上，如果您创建参与方 A.时选中复选框</span><span class="sxs-lookup"><span data-stu-id="f7128-111">All properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are enabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f7128-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="f7128-112">Prerequisites</span></span>  
 <span data-ttu-id="f7128-113">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="f7128-113">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-gs-and-st-segments"></a><span data-ttu-id="f7128-114">定义 GS 和 ST 段</span><span class="sxs-lookup"><span data-stu-id="f7128-114">To define the GS and ST segments</span></span>  
  
1.  <span data-ttu-id="f7128-115">创建 X12 编码协议，如中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="f7128-115">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="f7128-116">若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="f7128-116">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="f7128-117">在单向协议选项卡下**事务集设置**部分中，单击**信封**。</span><span class="sxs-lookup"><span data-stu-id="f7128-117">On a one-way agreement tab, under **Transaction Set Settings** section, click **Envelopes**.</span></span>  
  
3.  <span data-ttu-id="f7128-118">在网格的行中，输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="f7128-118">In a row of the grid, enter the following:</span></span>  
  
    -   <span data-ttu-id="f7128-119">有关**事务类型**字段中，为事务集标识符代码，从下拉列表中选择一个值。</span><span class="sxs-lookup"><span data-stu-id="f7128-119">For the **Transaction Type** field, select a value for the transaction set identifier code from the drop-down list.</span></span>  
  
    -   <span data-ttu-id="f7128-120">有关**版本/发行版**，输入包含最少一个字符，最多为 12 个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="f7128-120">For **Version/Release**, enter an alphanumeric value with a minimum of one character and a maximum of 12 characters.</span></span>  
  
    -   <span data-ttu-id="f7128-121">有关**目标命名空间**元素，从下拉列表中，选择一个值，或输入一个命名空间。</span><span class="sxs-lookup"><span data-stu-id="f7128-121">For **Target namespace** elements, select a value from the drop-down list, or enter a namespace.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f7128-122">这些将是 BizTalk Server 将与生成的交换关联的值进行比较的值。</span><span class="sxs-lookup"><span data-stu-id="f7128-122">These will be the values that BizTalk Server will compare with the values associated with the interchange it is building.</span></span>  
  
4.  <span data-ttu-id="f7128-123">在网格的同一行中，输入以下信息：</span><span class="sxs-lookup"><span data-stu-id="f7128-123">In the same row of the grid, enter the following:</span></span>  
  
    -   <span data-ttu-id="f7128-124">有关**GS1**，从下拉列表中选择的值为功能代码。</span><span class="sxs-lookup"><span data-stu-id="f7128-124">For **GS1**, select a value for the functional code from the drop-down list.</span></span> <span data-ttu-id="f7128-125">这是一个可选字段。</span><span class="sxs-lookup"><span data-stu-id="f7128-125">This is an optional field.</span></span>  
  
    -   <span data-ttu-id="f7128-126">有关**GS2**，为两个字符的最小值和最多 15 个字符的应用程序发送方输入的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="f7128-126">For **GS2**, enter an alphanumeric value for the application sender with a minimum of two characters and a maximum of 15 characters.</span></span> <span data-ttu-id="f7128-127">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="f7128-127">This is a required field.</span></span>  
  
    -   <span data-ttu-id="f7128-128">有关**GS3**，输入应用程序接收方最少包含 2 个字符，最多包含 15 个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="f7128-128">For **GS3**, enter an alphanumeric value for the application receiver with a minimum of two characters and a maximum of 15 characters.</span></span> <span data-ttu-id="f7128-129">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="f7128-129">This is a required field.</span></span>  
  
    -   <span data-ttu-id="f7128-130">有关**GS4**，选择**CCYYMMDD**或**YYMMDD**。</span><span class="sxs-lookup"><span data-stu-id="f7128-130">For **GS4**, select **CCYYMMDD** or **YYMMDD**.</span></span> <span data-ttu-id="f7128-131">这是一个可选字段</span><span class="sxs-lookup"><span data-stu-id="f7128-131">This is an optional field</span></span>  
  
    -   <span data-ttu-id="f7128-132">有关**GS5**，选择**HHMM**， **HHMMSS**，或者**HHMMSSdd**。</span><span class="sxs-lookup"><span data-stu-id="f7128-132">For **GS5**, select **HHMM**, **HHMMSS**, or **HHMMSSdd**.</span></span> <span data-ttu-id="f7128-133">这是一个可选字段</span><span class="sxs-lookup"><span data-stu-id="f7128-133">This is an optional field</span></span>  
  
    -   <span data-ttu-id="f7128-134">有关**GS7**，从下拉列表中选择负责代理的值。</span><span class="sxs-lookup"><span data-stu-id="f7128-134">For **GS7**, select a value for the responsible agency from the drop-down list.</span></span> <span data-ttu-id="f7128-135">这是一个可选字段。</span><span class="sxs-lookup"><span data-stu-id="f7128-135">This is an optional field.</span></span>  
  
    -   <span data-ttu-id="f7128-136">有关**GS8**，标识最少一个字符，最多为 12 个字符的文档中输入的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="f7128-136">For **GS8**, enter an alphanumeric value for the document identified with a minimum of one character and a maximum of 12 characters.</span></span> <span data-ttu-id="f7128-137">这是一个可选字段。</span><span class="sxs-lookup"><span data-stu-id="f7128-137">This is an optional field.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="f7128-138">这些将是 BizTalk Server 将在生成如果该交换的 GS 字段中输入的值**事务类型**，**版本/发行版**，和**目标命名空间**同一行中的元素是那些与交换关联的匹配项。</span><span class="sxs-lookup"><span data-stu-id="f7128-138">These will be the values that BizTalk Server will enter in the GS fields of the interchange it is building if the **Transaction Type**, **Version/Release**, and **Target namespace** elements in the same row are a match for those associated with the interchange.</span></span>  
  
5.  <span data-ttu-id="f7128-139">重复步骤 3 和 4 网格中输入其他行。</span><span class="sxs-lookup"><span data-stu-id="f7128-139">Repeat steps 3 and 4 to enter additional rows into the grid.</span></span>  
  
6.  <span data-ttu-id="f7128-140">在网格中的一个行，请单击**默认**以将其指定为默认行。</span><span class="sxs-lookup"><span data-stu-id="f7128-140">For one row in the grid, click **Default** to designate it as the default row.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f7128-141">如果消息没有与匹配**事务类型**，**版本/发行版**，并**目标命名空间**在任何行，BizTalk Server 中的元素将填充该消息替换为值**GS1**， **GS2**， **GS3**， **GS5**， **GS7**，和**GS8**默认行中的元素。</span><span class="sxs-lookup"><span data-stu-id="f7128-141">If a message does not have a match with the **Transaction Type**, **Version/Release**, and **Target namespace** elements in any row, BizTalk Server will populate the message with the values for the **GS1**, **GS2**, **GS3**, **GS5**, **GS7**, and **GS8** elements in the default row.</span></span> <span data-ttu-id="f7128-142">将使用这些值，即使该消息没有与匹配**事务类型**，**版本/发行版**，并**目标命名空间**默认行中的元素。</span><span class="sxs-lookup"><span data-stu-id="f7128-142">These values will be used even if the message does not have a match with the **Transaction Type**, **Version/Release**, and **Target namespace** elements of the default row.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f7128-143">如果没有默认值为所选的传入文档的不匹配**事务类型**，**版本/发行版**，并**目标命名空间**的任何行的元素将被挂起.</span><span class="sxs-lookup"><span data-stu-id="f7128-143">If no default is selected, incoming documents that do not match the **Transaction Type**, **Version/Release**, and **Target namespace** elements of any rows will be suspended.</span></span>  
  
7.  <span data-ttu-id="f7128-144">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="f7128-144">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7128-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7128-145">See Also</span></span>  
 [<span data-ttu-id="f7128-146">配置事务集设置 (X12)</span><span class="sxs-lookup"><span data-stu-id="f7128-146">Configuring Transaction Set Settings (X12)</span></span>](../core/configuring-transaction-set-settings-x12.md)