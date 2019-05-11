---
title: 配置本地主机设置 （X12-事务集设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e31b41c3-49fc-46ef-ab69-889e30dfc58e
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 897a8f5c9cacd84f8a54f06276c0170fba7045cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390835"
---
# <a name="configuring-local-host-settings-x12-transaction-set-settings"></a><span data-ttu-id="7054d-102">配置本地主机设置（X 12-事务集设置）</span><span class="sxs-lookup"><span data-stu-id="7054d-102">Configuring Local Host Settings (X12-Transaction Set Settings)</span></span>
<span data-ttu-id="7054d-103">若要处理传入的交换，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]必须确定它需要使用在处理和验证交换的架构。</span><span class="sxs-lookup"><span data-stu-id="7054d-103">To process an incoming interchange, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] must determine the schema that it needs to use in processing and validating the interchange.</span></span> <span data-ttu-id="7054d-104">这包括确定与架构相关联的目标命名空间并确定要使用的架构。</span><span class="sxs-lookup"><span data-stu-id="7054d-104">This consists of determining the target namespace associated with the schema, and determining the schema to be used.</span></span> <span data-ttu-id="7054d-105">在参与方协议的此页上，输入要在确定目标命名空间时使用的属性。</span><span class="sxs-lookup"><span data-stu-id="7054d-105">In this page of the party agreement, you enter the properties to be used in determining the target namespace.</span></span> <span data-ttu-id="7054d-106">如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]确定架构中，请参阅[协议解析、 架构发现和收到的 EDI 消息的授权](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md)。</span><span class="sxs-lookup"><span data-stu-id="7054d-106">How [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] determines the schema is described in [Agreement Resolution, Schema Discovery, and Authorization for Received EDI Messages](../core/agreement-resolution-schema-discovery-and-authorization-for-received-edi.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7054d-107">本主题还适用于与 HIPAA 相关的设置。</span><span class="sxs-lookup"><span data-stu-id="7054d-107">This topic applies also to HIPAA-related settings.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="7054d-108">没有属性上将禁用**参与方 A-> 参与方 B**单向协议选项卡，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**复选框为参与方 a。但是，禁用中相同页面上的所有属性**参与方 B-> 参与方 A**选项卡上，如果您创建参与方 A.时选中复选框</span><span class="sxs-lookup"><span data-stu-id="7054d-108">No properties are disabled on **Party A->Party B** one-way agreement tab if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box for Party A. However, all the properties are disabled on the same page in the **Party B->Party A** tab if you selected the check box while creating Party A.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="7054d-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="7054d-109">Prerequisites</span></span>  
 <span data-ttu-id="7054d-110">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="7054d-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
## <a name="determining-the-target-namespace"></a><span data-ttu-id="7054d-111">确定目标 Namespace</span><span class="sxs-lookup"><span data-stu-id="7054d-111">Determining the Target Namespace</span></span>  
 <span data-ttu-id="7054d-112">在中**自定义目标命名空间**网格中，您可以设为目标命名空间的命名空间之一的标准架构附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7054d-112">In the **Customize Target namespace** grid, you can set the target namespaces to one of the namespaces for the standard schemas shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="7054d-113">在网格中，将关联的值**目标 Namespace**使用的应用程序发送方的值的元素 (**GS2**) 和事务集标识符代码 (**ST1**)。</span><span class="sxs-lookup"><span data-stu-id="7054d-113">In the grid, you associate a value of the **Target Namespace** element with values of the application sender (**GS2**) and transaction set identifier code (**ST1**).</span></span> <span data-ttu-id="7054d-114">如果 BizTalk 接收一条消息的**GS2**并**ST1**数据元素与网格行中的匹配，BizTalk 将使用相应的命名空间来处理该消息。</span><span class="sxs-lookup"><span data-stu-id="7054d-114">When BizTalk receives a message whose **GS2** and **ST1** data elements match those in a row of the grid, BizTalk will use the corresponding namespace to process the message.</span></span> <span data-ttu-id="7054d-115">您输入的元素的值必须是唯一的。</span><span class="sxs-lookup"><span data-stu-id="7054d-115">The values of the elements that you enter must be unique.</span></span>  
  
 <span data-ttu-id="7054d-116">如果消息没有与匹配**GS2**并**ST1**网格中，BizTalk Server 的任何行中的数据元素将处理该消息的行中使用命名空间，为其**默认**列进行检查。</span><span class="sxs-lookup"><span data-stu-id="7054d-116">If a message does not have a match with the **GS2** and **ST1** data elements in any row of the grid, BizTalk Server will process the message using the namespace in the row for which the **Default** column is checked.</span></span> <span data-ttu-id="7054d-117">可用作默认目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="7054d-117">That serves as the default target namespace.</span></span> <span data-ttu-id="7054d-118">如果未不标识任何命名空间，BizTalk Server 将使用的默认命名空间`http://schemas.microsoft.com/BizTalk/Edi/EDIFACT/2006`。</span><span class="sxs-lookup"><span data-stu-id="7054d-118">If no namespace is identified, BizTalk Server will use the default namespace of `http://schemas.microsoft.com/BizTalk/Edi/EDIFACT/2006`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7054d-119">如果您在网格中，输入设置的任何字段，然后删除该设置，必须删除整行或该页的验证将失败。</span><span class="sxs-lookup"><span data-stu-id="7054d-119">If you enter a setting for any of the fields in the grid, and then delete that setting, you will have to delete the entire row or the page will fail validation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7054d-120">有关使用此网格中，运行完成 EDI 接口开发人员教程，专门设置参与方接收的交换中的说明。</span><span class="sxs-lookup"><span data-stu-id="7054d-120">For an illustration of using this grid, run through the EDI Interface Developer tutorial, specifically setting up a party to receive an interchange from.</span></span> <span data-ttu-id="7054d-121">有关详细信息，请参阅[步骤 4:为您的贸易合作伙伴配置参与方和业务配置文件](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md)。</span><span class="sxs-lookup"><span data-stu-id="7054d-121">For more information, see [Step 4: Configure a Party and Business Profile for Your Trading Partner](../core/step-4-configure-a-party-and-business-profile-for-your-trading-partner1.md).</span></span>  
  
### <a name="to-configure-local-host-settings-for-transaction-sets"></a><span data-ttu-id="7054d-122">若要配置本地主机设置为事务集</span><span class="sxs-lookup"><span data-stu-id="7054d-122">To configure local host settings for transaction sets</span></span>  
  
1.  <span data-ttu-id="7054d-123">创建 X12 编码协议，如中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="7054d-123">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="7054d-124">若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="7054d-124">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="7054d-125">在单向协议选项卡下**事务集设置**部分中，单击**本地主机设置**。</span><span class="sxs-lookup"><span data-stu-id="7054d-125">On a one-way agreement tab, under **Transaction Set Settings** section, click **Local Host Settings**.</span></span>  
  
3.  <span data-ttu-id="7054d-126">选择**将隐式小数格式 Nn 十进制数值**若要使用的中间 XML 中 BizTalk Server 的十进制数字值格式 Nn 指定的 EDI 数值转换。</span><span class="sxs-lookup"><span data-stu-id="7054d-126">Select **Convert implied decimal format Nn to base 10 numeric value** to convert an EDI number that is specified with the format Nn into a base-10 numeric value in the intermediate XML in BizTalk Server.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="7054d-127">在此转换后的中间 XML 可能无法通过长度验证。</span><span class="sxs-lookup"><span data-stu-id="7054d-127">After this conversion, the intermediate XML may fail length validation.</span></span> <span data-ttu-id="7054d-128">这是因为采用以 10 为基数的数字格式的数字包含小数点，使其长度超过一个以 Nn 格式。</span><span class="sxs-lookup"><span data-stu-id="7054d-128">This occurs because the number in the base-10 numeric format includes a decimal, making its length one greater than the number in Nn format.</span></span> <span data-ttu-id="7054d-129">可以通过添加的值来解决此问题**1**为最小/最大长度值。</span><span class="sxs-lookup"><span data-stu-id="7054d-129">You can resolve this issue by adding a value of **1** to the minimum/maximum length value.</span></span>  
  
4.  <span data-ttu-id="7054d-130">作为包含在事务集验证设置，如果将设置**尾部分隔符策略**到**可选**或**必需**，可以选择**创建空XML 标记为尾部分隔符**以使交换发送方包含为尾部分隔符的空 XML 标记。</span><span class="sxs-lookup"><span data-stu-id="7054d-130">As part of the transaction set validation settings, if you set **Trailing Separator Policy** to **Optional** or **Mandatory**, you can select **Create empty XML tags for trailing separators** to have the interchange sender include empty XML tags for trailing separators.</span></span>  
  
5.  <span data-ttu-id="7054d-131">在中**自定义目标 Namespace**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7054d-131">In the **Customize Target Namespace** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="7054d-132">选择**默认**包含你想要定义的默认目标命名空间的行的复选框。</span><span class="sxs-lookup"><span data-stu-id="7054d-132">Select the **Default** check box for the row that contains the default target namespace that you want to define.</span></span>  
  
    2.  <span data-ttu-id="7054d-133">在中**对于 ST1**列中，选择一个值为事务集标识符代码，从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="7054d-133">In the **For ST1** column, select a value for the Transaction set identifier code from the drop-down list.</span></span>  
  
    3.  <span data-ttu-id="7054d-134">在中**GS2**列中，输入应用程序发送方与两个字符的最小值和最多包含 15 个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="7054d-134">In the **GS2** column, enter an alphanumeric value for the Application sender with a minimum of two characters and a maximum of 15 characters.</span></span> <span data-ttu-id="7054d-135">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="7054d-135">This is a required field.</span></span>  
  
    4.  <span data-ttu-id="7054d-136">在中**目标 Namespace**列中，从下拉列表中选择或输入当网格的任意行中的数据元素与交换中的字段不存在任何匹配项时要使用的交换目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="7054d-136">In the **Target Namespace** column, select from the drop-down list or enter the target namespace to be used for an interchange when no match is found between the data elements in any row of the grid and the fields in the interchange.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="7054d-137">这些将是 BizTalk Server 将与它收到的交换关联的值进行比较的值。</span><span class="sxs-lookup"><span data-stu-id="7054d-137">These will be the values that BizTalk Server will compare with the values associated with the interchange it received.</span></span>  
  
    5.  <span data-ttu-id="7054d-138">重复这些步骤的任何其他目标命名空间使用。</span><span class="sxs-lookup"><span data-stu-id="7054d-138">Repeat these steps for any other target namespaces to be used.</span></span>  
  
    6.  <span data-ttu-id="7054d-139">若要从列表中删除目标命名空间，选择的行，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="7054d-139">To remove a target namespace from the list, select the row and click **Delete**.</span></span>  
  
6.  <span data-ttu-id="7054d-140">单击**Apply**以接受更改，或单击**确定**以输入和验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="7054d-140">Click **Apply** to accept the changes, or click **OK** to enter and validate the changes, and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7054d-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="7054d-141">See Also</span></span>  
 [<span data-ttu-id="7054d-142">配置事务集设置 (X12)</span><span class="sxs-lookup"><span data-stu-id="7054d-142">Configuring Transaction Set Settings (X12)</span></span>](../core/configuring-transaction-set-settings-x12.md)