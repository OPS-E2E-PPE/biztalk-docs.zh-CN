---
title: 配置本地主机设置 （EDIFACT-事务集设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9f7c9cb9-7b4b-41de-a3f3-c0519b18673c
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d918e422384a68875e2bf6625ca983c1819f1d61
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390928"
---
# <a name="configuring-local-host-settings-edifact-transaction-set-settings"></a><span data-ttu-id="5a68e-102">配置本地主机设置（EDIFACT-事务集设置）</span><span class="sxs-lookup"><span data-stu-id="5a68e-102">Configuring Local Host Settings (EDIFACT-Transaction Set Settings)</span></span>
<span data-ttu-id="5a68e-103">若要处理传入的交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]必须确定它需要使用在处理和验证交换的架构。</span><span class="sxs-lookup"><span data-stu-id="5a68e-103">To process an incoming interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] must determine the schema that it needs to use in processing and validating the interchange.</span></span> <span data-ttu-id="5a68e-104">这包括确定与架构相关联的目标命名空间并确定要使用的架构。</span><span class="sxs-lookup"><span data-stu-id="5a68e-104">This consists of determining the target namespace associated with the schema, and determining the schema to be used.</span></span> <span data-ttu-id="5a68e-105">在参与方协议的此页上，输入要在确定目标命名空间时使用的属性。</span><span class="sxs-lookup"><span data-stu-id="5a68e-105">In this page of the party agreement, you enter the properties to be used in determining the target namespace.</span></span> <span data-ttu-id="5a68e-106">BizTalk Server 如何确定架构中所述[协议解析、 架构发现和收到的 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)。</span><span class="sxs-lookup"><span data-stu-id="5a68e-106">How BizTalk Server determines the schema is described in [Agreement Resolution, Schema Discovery, and Authorization for Received EDI Messages](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5a68e-107">没有属性上将禁用**参与方 A-> 参与方 B**单向协议选项卡，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**复选框为参与方 a。但是，禁用中相同页面上的所有属性**参与方 B-> 参与方 A**选项卡上，如果您创建参与方 A.时选中复选框</span><span class="sxs-lookup"><span data-stu-id="5a68e-107">No properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are disabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5a68e-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="5a68e-108">Prerequisites</span></span>  
 <span data-ttu-id="5a68e-109">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="5a68e-109">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="determining-the-target-namespace"></a><span data-ttu-id="5a68e-110">确定目标 Namespace</span><span class="sxs-lookup"><span data-stu-id="5a68e-110">Determining the Target Namespace</span></span>  
 <span data-ttu-id="5a68e-111">在中**自定义目标 Namespace**网格中，可以将目标命名空间设置为与 Microsoft 一起提供的标准架构的命名空间之一[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5a68e-111">In the **Customize Target Namespace** grid, you can set the target namespace to one of the namespaces for the standard schemas shipped with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="5a68e-112">在网格中，将关联的值**目标 Namespace**具有值的元素**UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**， **UNG2.1**，并**UNG2.2**元素。</span><span class="sxs-lookup"><span data-stu-id="5a68e-112">In the grid, you associate a value of the **Target Namespace** element with values of the **UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, **UNG2.1**, and **UNG2.2** elements.</span></span> <span data-ttu-id="5a68e-113">如果 BizTalk 接收一条消息的**UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**， **UNG2.1**，和**UNG2.2**元素与网格行中匹配，BizTalk 将使用相应的命名空间来确定它将用于处理该消息的架构。</span><span class="sxs-lookup"><span data-stu-id="5a68e-113">When BizTalk receives a message whose **UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, **UNG2.1**, and **UNG2.2** elements match those in a row of the grid, BizTalk will use the corresponding namespace to determine the schema that it will use to process the message.</span></span> <span data-ttu-id="5a68e-114">您输入的元素的值必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="5a68e-114">The values of the elements that you enter must be unique.</span></span>  
  
 <span data-ttu-id="5a68e-115">如果消息没有与匹配**UNH2.1**， **UNH2.2**， **UNH2.3**， **UNH2.5**， **UNG2.1**，并**UNG2.2**网格中，BizTalk Server 的任意行中的元素将处理该消息为其行中使用命名空间**默认**选中列。</span><span class="sxs-lookup"><span data-stu-id="5a68e-115">If a message does not have a match with the **UNH2.1**, **UNH2.2**, **UNH2.3**, **UNH2.5**, **UNG2.1**, and **UNG2.2** elements in any row of the grid, BizTalk Server will process the message using the namespace in the row for which the **Default** column is checked.</span></span> <span data-ttu-id="5a68e-116">可用作默认目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="5a68e-116">That serves as the default target namespace.</span></span> <span data-ttu-id="5a68e-117">如果未不标识任何命名空间，BizTalk 将使用的默认命名空间`http://schemas.microsoft.com/BizTalk/Edi/Edifact/2006`。</span><span class="sxs-lookup"><span data-stu-id="5a68e-117">If no namespace is identified, BizTalk will use the default namespace of `http://schemas.microsoft.com/BizTalk/Edi/Edifact/2006`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5a68e-118">如果您在网格中，输入设置的任何字段，然后删除该设置，必须删除整行或该页的验证将失败。</span><span class="sxs-lookup"><span data-stu-id="5a68e-118">If you enter a setting for any of the fields in the grid, and then delete that setting, you will have to delete the entire row or the page will fail validation.</span></span>  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a><span data-ttu-id="5a68e-119">若要配置本地主机设置为事务集</span><span class="sxs-lookup"><span data-stu-id="5a68e-119">To configure local host settings for transaction sets</span></span>  
  
1.  <span data-ttu-id="5a68e-120">创建 EDIFACT 编码协议，如中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。</span><span class="sxs-lookup"><span data-stu-id="5a68e-120">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="5a68e-121">若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="5a68e-121">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="5a68e-122">在单向协议选项卡下**事务集设置**部分中，单击**本地主机设置**。</span><span class="sxs-lookup"><span data-stu-id="5a68e-122">On a one-way agreement tab, under **Transaction Set Settings** section, click **Local Host Settings**.</span></span>  
  
3.  <span data-ttu-id="5a68e-123">作为包含在事务集验证设置，如果将设置**尾部分隔符策略**到**可选**或**必需**，可以选择**创建空XML 标记为尾部分隔符**以使交换发送方包含为尾部分隔符的空 XML 标记。</span><span class="sxs-lookup"><span data-stu-id="5a68e-123">As part of the transaction set validation settings, if you set **Trailing Separator Policy** to **Optional** or **Mandatory**, you can select **Create empty XML tags for trailing separators** to have the interchange sender include empty XML tags for trailing separators.</span></span>  
  
4.  <span data-ttu-id="5a68e-124">选择**使用点 （.） 作为小数分隔符**启用 BizTalk Server 中包含点 （.） 包含十进制数的交换外创建的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="5a68e-124">Select **Use Dot (.) as decimal separator** to enable BizTalk Server include a dot (.) in the XML message created out of an interchange that contains a decimal number.</span></span>  
  
5.  <span data-ttu-id="5a68e-125">在中**自定义目标 Namespace**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5a68e-125">In the **Customize Target Namespace** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="5a68e-126">选择**默认**包含你想要定义的默认目标命名空间的行的复选框。</span><span class="sxs-lookup"><span data-stu-id="5a68e-126">Select the **Default** check box for the row that contains the default target namespace that you want to define.</span></span>  
  
    2.  <span data-ttu-id="5a68e-127">在中**UNH2.1**列中，指定消息类型。</span><span class="sxs-lookup"><span data-stu-id="5a68e-127">In the **UNH2.1** column, specify the message type.</span></span> <span data-ttu-id="5a68e-128">（最多六个字符）。</span><span class="sxs-lookup"><span data-stu-id="5a68e-128">(maximum, six characters).</span></span>  
  
    3.  <span data-ttu-id="5a68e-129">在中**UNH2.2**列中，指定消息版本号。</span><span class="sxs-lookup"><span data-stu-id="5a68e-129">In the **UNH2.2**  column, specify the message version number.</span></span> <span data-ttu-id="5a68e-130">（最小值、 一个字符; 最多三个字符）。</span><span class="sxs-lookup"><span data-stu-id="5a68e-130">(minimum, one character; maximum, three characters).</span></span>  
  
    4.  <span data-ttu-id="5a68e-131">在中**UNH2.3**列中，指定消息发行版号。</span><span class="sxs-lookup"><span data-stu-id="5a68e-131">In the **UNH2.3** column, specify the message release number.</span></span> <span data-ttu-id="5a68e-132">（最小值、 一个字符; 最多三个字符）。</span><span class="sxs-lookup"><span data-stu-id="5a68e-132">(minimum, one character; maximum, three characters).</span></span>  
  
    5.  <span data-ttu-id="5a68e-133">在中**UNH2.5**列中，指定分配的代码。</span><span class="sxs-lookup"><span data-stu-id="5a68e-133">In the **UNH2.5** column, specify the assigned code.</span></span> <span data-ttu-id="5a68e-134">（最多六个字符。</span><span class="sxs-lookup"><span data-stu-id="5a68e-134">(maximum, six characters.</span></span> <span data-ttu-id="5a68e-135">必须为字母数字）。</span><span class="sxs-lookup"><span data-stu-id="5a68e-135">Must be alphanumeric).</span></span>  
  
    6.  <span data-ttu-id="5a68e-136">在中**UNG2.1**列中，输入应用程序发件人的标识具有最少的一个字符，最多为 35 个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="5a68e-136">In the **UNG2.1** column, enter an alphanumeric value for the application sender identification with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="5a68e-137">此字段是必需的。</span><span class="sxs-lookup"><span data-stu-id="5a68e-137">This field is required.</span></span>  
  
    7.  <span data-ttu-id="5a68e-138">在中**UNG2.2**列中，为最少一个字符，最多四个字符的应用程序发送方代码限定符输入一个字母数字值。</span><span class="sxs-lookup"><span data-stu-id="5a68e-138">In the **UNG2.2** column, enter an alphanumeric value for the application sender code qualifier with a minimum of one character and a maximum of four characters.</span></span> <span data-ttu-id="5a68e-139">此字段是可选的。</span><span class="sxs-lookup"><span data-stu-id="5a68e-139">This field is optional.</span></span>  
  
    8.  <span data-ttu-id="5a68e-140">在中**目标 Namespace**列中，从下拉列表中选择或输入当网格的任意行中的数据元素与交换中的字段不存在任何匹配项时要使用的交换目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="5a68e-140">In the **Target Namespace** column, select from the drop-down list or enter the target namespace to be used for an interchange when no match is found between the data elements in any row of the grid and the fields in the interchange.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="5a68e-141">这些将是 BizTalk Server 将与它收到的交换关联的值进行比较的值。</span><span class="sxs-lookup"><span data-stu-id="5a68e-141">These will be the values that BizTalk Server will compare with the values associated with the interchange it received.</span></span>  
  
    9. <span data-ttu-id="5a68e-142">重复这些步骤的任何其他目标命名空间使用。</span><span class="sxs-lookup"><span data-stu-id="5a68e-142">Repeat these steps for any other target namespaces to be used.</span></span>  
  
    10. <span data-ttu-id="5a68e-143">若要从列表中删除目标命名空间，选择的行，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="5a68e-143">To remove a target namespace from the list, select the row and click **Delete**.</span></span>  
  
6.  <span data-ttu-id="5a68e-144">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="5a68e-144">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a68e-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="5a68e-145">See Also</span></span>  
 [<span data-ttu-id="5a68e-146">配置事务集设置 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="5a68e-146">Configuring Transaction Set Settings (EDIFACT)</span></span>](../core/configuring-transaction-set-settings-edifact.md)