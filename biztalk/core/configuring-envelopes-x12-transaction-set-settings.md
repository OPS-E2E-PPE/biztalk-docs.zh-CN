---
title: "配置信封 （X12 事务集设置） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9313a7b9-72fa-4071-8c65-007371643179
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 519062fa4647cdc2c7c39dda19373ff888eaf601
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-envelopes-x12-transaction-set-settings"></a><span data-ttu-id="a7930-102">配置信封（X12--事务集设置）</span><span class="sxs-lookup"><span data-stu-id="a7930-102">Configuring Envelopes (X12-Transaction Set Settings)</span></span>
<span data-ttu-id="a7930-103">在**Envelops**页**事务设置设置**部分中，你定义 BizTalk Server 如何生成它将发送到方的 X12 编码交换的 GS 和 ST 段。</span><span class="sxs-lookup"><span data-stu-id="a7930-103">In the **Envelops** page of the **Transaction Set Settings** section, you define how BizTalk Server generates the GS and ST segments for an X12-encoded interchange that it sends to the party.</span></span> <span data-ttu-id="a7930-104">GS 段为 X12 编码的交换标识和指定功能组。</span><span class="sxs-lookup"><span data-stu-id="a7930-104">A GS segment identifies and specifies a functional group for an X12-encoded interchange.</span></span> <span data-ttu-id="a7930-105">ST 段是 X12 编码的交换的消息标头。</span><span class="sxs-lookup"><span data-stu-id="a7930-105">An ST segment is the message header for an X12-encoded interchange.</span></span>  
  
 <span data-ttu-id="a7930-106">在此页上，你将相关联的值**GS1**， **GS2**， **GS3**， **GS4**， **GS5**， **GS7**，和**GS8**具有的值的数据元素**事务类型**，**版本/发行版**，和**目标命名空间**数据元素。</span><span class="sxs-lookup"><span data-stu-id="a7930-106">In this page, you associate values of the **GS1**, **GS2**, **GS3**, **GS4**, **GS5**, **GS7**, and **GS8** data elements with values of the **Transaction Type**, **Version/Release**, and **Target namespace** data elements.</span></span> <span data-ttu-id="a7930-107">BizTalk 确定 BizTalk XML 消息已设置的值**事务类型**，**版本/发行版**，和**目标命名空间**的网格中，行中的元素BizTalk 将填充**GS1**， **GS2**， **GS3**， **GS4**， **GS5**， **GS7**，和**GS8**同一行的网格中的值交换的信封中的传出数据元素。</span><span class="sxs-lookup"><span data-stu-id="a7930-107">When BizTalk determines that a BizTalk XML message has the values set for the **Transaction Type**, **Version/Release**, and **Target namespace** elements in a row of the grid, BizTalk will populate the **GS1**, **GS2**, **GS3**, **GS4**, **GS5**, **GS7**, and **GS8** data elements in the envelope of the outgoing interchange with the values from the same row of the grid.</span></span> <span data-ttu-id="a7930-108">值**事务类型**，**版本/发行版**，和**目标命名空间**元素必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="a7930-108">The values of the **Transaction Type**, **Version/Release**, and **Target namespace** elements must be unique.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7930-109">如果为网格中的任意字段输入设置，然后删除该设置，则必须删除整行，否则对该页的验证将失败。</span><span class="sxs-lookup"><span data-stu-id="a7930-109">If you enter a setting for any of the fields in the grid, and then delete that setting, you will have to delete the entire row or the page will fail validation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a7930-110">本主题还适用于与 HIPAA 相关的设置。</span><span class="sxs-lookup"><span data-stu-id="a7930-110">This topic applies also to HIPAA-related settings.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="a7930-111">所有属性上将都禁用**A 方-> 方 B**单向协议选项卡，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**检查框 a 方。但是，在中相同页面上启用的所有属性**B 方-> A 方**选项卡上，如果创建 a 方。 时选中复选框</span><span class="sxs-lookup"><span data-stu-id="a7930-111">All properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are enabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a7930-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="a7930-112">Prerequisites</span></span>  
 <span data-ttu-id="a7930-113">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="a7930-113">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-gs-and-st-segments"></a><span data-ttu-id="a7930-114">若要定义 GS 和 ST 段</span><span class="sxs-lookup"><span data-stu-id="a7930-114">To define the GS and ST segments</span></span>  
  
1.  <span data-ttu-id="a7930-115">创建 X12 编码协议中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="a7930-115">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="a7930-116">若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="a7930-116">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="a7930-117">单向协议选项卡上，在**事务设置设置**部分中，单击**包络线**。</span><span class="sxs-lookup"><span data-stu-id="a7930-117">On a one-way agreement tab, under **Transaction Set Settings** section, click **Envelopes**.</span></span>  
  
3.  <span data-ttu-id="a7930-118">在网格的某行中，输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="a7930-118">In a row of the grid, enter the following:</span></span>  
  
    -   <span data-ttu-id="a7930-119">有关**事务类型**字段中，为事务集标识符代码，从下拉列表中选择一个值。</span><span class="sxs-lookup"><span data-stu-id="a7930-119">For the **Transaction Type** field, select a value for the transaction set identifier code from the drop-down list.</span></span>  
  
    -   <span data-ttu-id="a7930-120">有关**版本/发行版**，输入一个字母数字值，该值最少包含一个字符，最多 12 个字符。</span><span class="sxs-lookup"><span data-stu-id="a7930-120">For **Version/Release**, enter an alphanumeric value with a minimum of one character and a maximum of 12 characters.</span></span>  
  
    -   <span data-ttu-id="a7930-121">有关**目标命名空间**元素，从下拉列表中，选择一个值，或输入命名空间。</span><span class="sxs-lookup"><span data-stu-id="a7930-121">For **Target namespace** elements, select a value from the drop-down list, or enter a namespace.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a7930-122">BizTalk Server 会将这些值与它所生成的交换的关联值进行比较。</span><span class="sxs-lookup"><span data-stu-id="a7930-122">These will be the values that BizTalk Server will compare with the values associated with the interchange it is building.</span></span>  
  
4.  <span data-ttu-id="a7930-123">在同一行网格中，输入以下内容：</span><span class="sxs-lookup"><span data-stu-id="a7930-123">In the same row of the grid, enter the following:</span></span>  
  
    -   <span data-ttu-id="a7930-124">有关**GS1**，从下拉列表中选择的功能的代码的值。</span><span class="sxs-lookup"><span data-stu-id="a7930-124">For **GS1**, select a value for the functional code from the drop-down list.</span></span> <span data-ttu-id="a7930-125">此字段为可选字段。</span><span class="sxs-lookup"><span data-stu-id="a7930-125">This is an optional field.</span></span>  
  
    -   <span data-ttu-id="a7930-126">有关**GS2**，不少于两个字符，最多包含 15 个字符的该应用程序发件人输入一个字母数字值。</span><span class="sxs-lookup"><span data-stu-id="a7930-126">For **GS2**, enter an alphanumeric value for the application sender with a minimum of two characters and a maximum of 15 characters.</span></span> <span data-ttu-id="a7930-127">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="a7930-127">This is a required field.</span></span>  
  
    -   <span data-ttu-id="a7930-128">有关**GS3**，为两个字符的最小值和最多 15 个字符的应用程序收件人输入一个字母数字值。</span><span class="sxs-lookup"><span data-stu-id="a7930-128">For **GS3**, enter an alphanumeric value for the application receiver with a minimum of two characters and a maximum of 15 characters.</span></span> <span data-ttu-id="a7930-129">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="a7930-129">This is a required field.</span></span>  
  
    -   <span data-ttu-id="a7930-130">有关**GS4**，选择**CCYYMMDD**或**YYMMDD**。</span><span class="sxs-lookup"><span data-stu-id="a7930-130">For **GS4**, select **CCYYMMDD** or **YYMMDD**.</span></span> <span data-ttu-id="a7930-131">此字段为可选字段</span><span class="sxs-lookup"><span data-stu-id="a7930-131">This is an optional field</span></span>  
  
    -   <span data-ttu-id="a7930-132">有关**GS5**，选择**HHMM**， **HHMMSS**，或**HHMMSSdd**。</span><span class="sxs-lookup"><span data-stu-id="a7930-132">For **GS5**, select **HHMM**, **HHMMSS**, or **HHMMSSdd**.</span></span> <span data-ttu-id="a7930-133">此字段为可选字段</span><span class="sxs-lookup"><span data-stu-id="a7930-133">This is an optional field</span></span>  
  
    -   <span data-ttu-id="a7930-134">有关**GS7**，从下拉列表中选择一个值为责任代理。</span><span class="sxs-lookup"><span data-stu-id="a7930-134">For **GS7**, select a value for the responsible agency from the drop-down list.</span></span> <span data-ttu-id="a7930-135">此字段为可选字段。</span><span class="sxs-lookup"><span data-stu-id="a7930-135">This is an optional field.</span></span>  
  
    -   <span data-ttu-id="a7930-136">有关**GS8**，为标识最少包含一个字符，最多 12 个字符的文档输入一个字母数字值。</span><span class="sxs-lookup"><span data-stu-id="a7930-136">For **GS8**, enter an alphanumeric value for the document identified with a minimum of one character and a maximum of 12 characters.</span></span> <span data-ttu-id="a7930-137">此字段为可选字段。</span><span class="sxs-lookup"><span data-stu-id="a7930-137">This is an optional field.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="a7930-138">这些将是 BizTalk Server 将生成如果该交换的 GS 字段中输入的值**事务类型**，**版本/发行版**，和**目标命名空间**同一行中的元素是交换关联的匹配项。</span><span class="sxs-lookup"><span data-stu-id="a7930-138">These will be the values that BizTalk Server will enter in the GS fields of the interchange it is building if the **Transaction Type**, **Version/Release**, and **Target namespace** elements in the same row are a match for those associated with the interchange.</span></span>  
  
5.  <span data-ttu-id="a7930-139">要在网格中输入其他行，请重复步骤 3 和步骤 4。</span><span class="sxs-lookup"><span data-stu-id="a7930-139">Repeat steps 3 and 4 to enter additional rows into the grid.</span></span>  
  
6.  <span data-ttu-id="a7930-140">对于在网格中的一个行，请单击**默认**以将其指定为默认行。</span><span class="sxs-lookup"><span data-stu-id="a7930-140">For one row in the grid, click **Default** to designate it as the default row.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a7930-141">如果消息没有包含的匹配项**事务类型**，**版本/发行版**，和**目标命名空间**任何行，BizTalk Server 中的元素将填充消息值**GS1**， **GS2**， **GS3**， **GS5**， **GS7**，和**GS8**默认行中的元素。</span><span class="sxs-lookup"><span data-stu-id="a7930-141">If a message does not have a match with the **Transaction Type**, **Version/Release**, and **Target namespace** elements in any row, BizTalk Server will populate the message with the values for the **GS1**, **GS2**, **GS3**, **GS5**, **GS7**, and **GS8** elements in the default row.</span></span> <span data-ttu-id="a7930-142">将使用这些值，即使消息不具有与匹配**事务类型**，**版本/发行版**，和**目标命名空间**默认行的元素。</span><span class="sxs-lookup"><span data-stu-id="a7930-142">These values will be used even if the message does not have a match with the **Transaction Type**, **Version/Release**, and **Target namespace** elements of the default row.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a7930-143">如果没有默认值是不匹配的已选定、 传入文档**事务类型**，**版本/发行版**，和**目标命名空间**的任何行的元素将被挂起.</span><span class="sxs-lookup"><span data-stu-id="a7930-143">If no default is selected, incoming documents that do not match the **Transaction Type**, **Version/Release**, and **Target namespace** elements of any rows will be suspended.</span></span>  
  
7.  <span data-ttu-id="a7930-144">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="a7930-144">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7930-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7930-145">See Also</span></span>  
 [<span data-ttu-id="a7930-146">配置事务集设置 (X12)</span><span class="sxs-lookup"><span data-stu-id="a7930-146">Configuring Transaction Set Settings (X12)</span></span>](../core/configuring-transaction-set-settings-x12.md)