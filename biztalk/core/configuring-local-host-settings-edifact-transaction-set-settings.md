---
title: "配置本地主机设置 （EDIFACT 事务集设置） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f7c9cb9-7b4b-41de-a3f3-c0519b18673c
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 912af3a047f77f077bf9de58a25802f3c658e6b0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-local-host-settings-edifact-transaction-set-settings"></a><span data-ttu-id="6644f-102">配置本地主机设置（EDIFACT-事务集设置）</span><span class="sxs-lookup"><span data-stu-id="6644f-102">Configuring Local Host Settings (EDIFACT-Transaction Set Settings)</span></span>
<span data-ttu-id="6644f-103">为了处理传入的交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 必须确定在处理和验证交换时需要使用的架构。</span><span class="sxs-lookup"><span data-stu-id="6644f-103">To process an incoming interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] must determine the schema that it needs to use in processing and validating the interchange.</span></span> <span data-ttu-id="6644f-104">这包括确定与架构关联的目标命名空间和确定要使用的架构。</span><span class="sxs-lookup"><span data-stu-id="6644f-104">This consists of determining the target namespace associated with the schema, and determining the schema to be used.</span></span> <span data-ttu-id="6644f-105">在参与方协议的此页中，可输入要在确定目标命名空间时使用的属性。</span><span class="sxs-lookup"><span data-stu-id="6644f-105">In this page of the party agreement, you enter the properties to be used in determining the target namespace.</span></span> <span data-ttu-id="6644f-106">中所述 BizTalk Server 如何确定架构[协议解析、 架构发现和接收 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)。</span><span class="sxs-lookup"><span data-stu-id="6644f-106">How BizTalk Server determines the schema is described in [Agreement Resolution, Schema Discovery, and Authorization for Received EDI Messages](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6644f-107">没有属性上将禁用**A 方-> 方 B**单向协议选项卡，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**复选框当事方 a。但是，将所有属性都禁用中相同页面上**B 方-> A 方**选项卡上，如果创建 a 方。 时选中复选框</span><span class="sxs-lookup"><span data-stu-id="6644f-107">No properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are disabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6644f-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="6644f-108">Prerequisites</span></span>  
 <span data-ttu-id="6644f-109">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="6644f-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="determining-the-target-namespace"></a><span data-ttu-id="6644f-110">确定目标命名空间</span><span class="sxs-lookup"><span data-stu-id="6644f-110">Determining the Target Namespace</span></span>  
 <span data-ttu-id="6644f-111">在**自定义目标 Namespace**网格中，可以将目标命名空间设置为随 Microsoft 提供的标准架构命名空间之一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6644f-111">In the **Customize Target Namespace** grid, you can set the target namespace to one of the namespaces for the standard schemas shipped with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="6644f-112">在网格中，你将关联的值**目标 Namespace**具有值的元素**UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**， **UNG2.1**，和**UNG2.2**元素。</span><span class="sxs-lookup"><span data-stu-id="6644f-112">In the grid, you associate a value of the **Target Namespace** element with values of the **UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, **UNG2.1**, and **UNG2.2** elements.</span></span> <span data-ttu-id="6644f-113">当 BizTalk 收到一条消息其**UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**， **UNG2.1**，和**UNG2.2**元素匹配的行的网格中，BizTalk 将使用相应的命名空间来确定它将用于处理消息的架构。</span><span class="sxs-lookup"><span data-stu-id="6644f-113">When BizTalk receives a message whose **UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, **UNG2.1**, and **UNG2.2** elements match those in a row of the grid, BizTalk will use the corresponding namespace to determine the schema that it will use to process the message.</span></span> <span data-ttu-id="6644f-114">输入的元素的值必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="6644f-114">The values of the elements that you enter must be unique.</span></span>  
  
 <span data-ttu-id="6644f-115">如果消息没有包含的匹配项**UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**， **UNG2.1**，和**UNG2.2**任何行网格中，BizTalk Server 中的元素将处理该消息为其行中使用命名空间**默认**列进行检查。</span><span class="sxs-lookup"><span data-stu-id="6644f-115">If a message does not have a match with the **UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, **UNG2.1**, and **UNG2.2** elements in any row of the grid, BizTalk Server will process the message using the namespace in the row for which the **Default** column is checked.</span></span> <span data-ttu-id="6644f-116">可以作为默认目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="6644f-116">That serves as the default target namespace.</span></span> <span data-ttu-id="6644f-117">如果未标识命名空间，则 BizTalk 将使用 `http://schemas.microsoft.com/BizTalk/Edi/Edifact/2006` 的默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="6644f-117">If no namespace is identified, BizTalk will use the default namespace of `http://schemas.microsoft.com/BizTalk/Edi/Edifact/2006`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6644f-118">如果为网格中的任意字段输入设置，然后删除该设置，则必须删除整行，否则对该页的验证将失败。</span><span class="sxs-lookup"><span data-stu-id="6644f-118">If you enter a setting for any of the fields in the grid, and then delete that setting, you will have to delete the entire row or the page will fail validation.</span></span>  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a><span data-ttu-id="6644f-119">要配置事务集的本地主机设置，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6644f-119">To configure local host settings for transaction sets</span></span>  
  
1.  <span data-ttu-id="6644f-120">创建 EDIFACT 编码协议中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。</span><span class="sxs-lookup"><span data-stu-id="6644f-120">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="6644f-121">若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="6644f-121">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="6644f-122">单向协议选项卡上，在**事务设置设置**部分中，单击**本地主机设置**。</span><span class="sxs-lookup"><span data-stu-id="6644f-122">On a one-way agreement tab, under **Transaction Set Settings** section, click **Local Host Settings**.</span></span>  
  
3.  <span data-ttu-id="6644f-123">因为该事务的一部分设置验证设置，如果你设置**尾随分隔符策略**到**可选**或**必需**，你可以选择**创建空XML 标记为尾随分隔符**能够包含的尾随分隔符的空 XML 标记交换发件人。</span><span class="sxs-lookup"><span data-stu-id="6644f-123">As part of the transaction set validation settings, if you set **Trailing Separator Policy** to **Optional** or **Mandatory**, you can select **Create empty XML tags for trailing separators** to have the interchange sender include empty XML tags for trailing separators.</span></span>  
  
4.  <span data-ttu-id="6644f-124">选择**使用点 （.） 作为小数分隔符**若要启用 BizTalk Server 包括句点 （.） 中包含的小数的交换创建的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="6644f-124">Select **Use Dot (.) as decimal separator** to enable BizTalk Server include a dot (.) in the XML message created out of an interchange that contains a decimal number.</span></span>  
  
5.  <span data-ttu-id="6644f-125">在**自定义目标 Namespace**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6644f-125">In the **Customize Target Namespace** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="6644f-126">选择**默认**包含你想要定义的默认目标命名空间的行的复选框。</span><span class="sxs-lookup"><span data-stu-id="6644f-126">Select the **Default** check box for the row that contains the default target namespace that you want to define.</span></span>  
  
    2.  <span data-ttu-id="6644f-127">在**UNH2.1**列中，指定消息类型。</span><span class="sxs-lookup"><span data-stu-id="6644f-127">In the **UNH2.1** column, specify the message type.</span></span> <span data-ttu-id="6644f-128">（最多六个字符）。</span><span class="sxs-lookup"><span data-stu-id="6644f-128">(maximum, six characters).</span></span>  
  
    3.  <span data-ttu-id="6644f-129">在**UNH2.2**列中，指定消息的版本号。</span><span class="sxs-lookup"><span data-stu-id="6644f-129">In the **UNH2.2**  column, specify the message version number.</span></span> <span data-ttu-id="6644f-130">（最小值、 一个字符; 最多三个字符）。</span><span class="sxs-lookup"><span data-stu-id="6644f-130">(minimum, one character; maximum, three characters).</span></span>  
  
    4.  <span data-ttu-id="6644f-131">在**UNH2.3**列中，指定消息发行版号。</span><span class="sxs-lookup"><span data-stu-id="6644f-131">In the **UNH2.3** column, specify the message release number.</span></span> <span data-ttu-id="6644f-132">（最小值、 一个字符; 最多三个字符）。</span><span class="sxs-lookup"><span data-stu-id="6644f-132">(minimum, one character; maximum, three characters).</span></span>  
  
    5.  <span data-ttu-id="6644f-133">在**UNH2.5**列中，指定所分配的代码。</span><span class="sxs-lookup"><span data-stu-id="6644f-133">In the **UNH2.5** column, specify the assigned code.</span></span> <span data-ttu-id="6644f-134">（最多六个字符。</span><span class="sxs-lookup"><span data-stu-id="6644f-134">(maximum, six characters.</span></span> <span data-ttu-id="6644f-135">必须为字母数字值）。</span><span class="sxs-lookup"><span data-stu-id="6644f-135">Must be alphanumeric).</span></span>  
  
    6.  <span data-ttu-id="6644f-136">在**UNG2.1**列中，输入应用程序发件人的标识具有最少的一个字符，最多 35 个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="6644f-136">In the **UNG2.1** column, enter an alphanumeric value for the application sender identification with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="6644f-137">此字段为必填字段。</span><span class="sxs-lookup"><span data-stu-id="6644f-137">This field is required.</span></span>  
  
    7.  <span data-ttu-id="6644f-138">在**UNG2.2**列中，输入最少包含一个字符，最多四个字符的应用程序发件人代码限定符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="6644f-138">In the **UNG2.2** column, enter an alphanumeric value for the application sender code qualifier with a minimum of one character and a maximum of four characters.</span></span> <span data-ttu-id="6644f-139">此字段是可选的。</span><span class="sxs-lookup"><span data-stu-id="6644f-139">This field is optional.</span></span>  
  
    8.  <span data-ttu-id="6644f-140">在**目标 Namespace**列中，从下拉列表中选择或输入要网格的任何行中的数据元素和交换中的字段之间未不找到任何匹配时使用的交换的目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="6644f-140">In the **Target Namespace** column, select from the drop-down list or enter the target namespace to be used for an interchange when no match is found between the data elements in any row of the grid and the fields in the interchange.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="6644f-141">BizTalk Server 会将这些值与它所收到的交换的关联值进行比较。</span><span class="sxs-lookup"><span data-stu-id="6644f-141">These will be the values that BizTalk Server will compare with the values associated with the interchange it received.</span></span>  
  
    9. <span data-ttu-id="6644f-142">对任何其他要使用的目标命名空间，重复这些步骤，</span><span class="sxs-lookup"><span data-stu-id="6644f-142">Repeat these steps for any other target namespaces to be used.</span></span>  
  
    10. <span data-ttu-id="6644f-143">若要从列表中删除目标命名空间，请选择行，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="6644f-143">To remove a target namespace from the list, select the row and click **Delete**.</span></span>  
  
6.  <span data-ttu-id="6644f-144">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="6644f-144">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6644f-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6644f-145">See Also</span></span>  
 [<span data-ttu-id="6644f-146">配置事务集设置 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="6644f-146">Configuring Transaction Set Settings (EDIFACT)</span></span>](../core/configuring-transaction-set-settings-edifact.md)