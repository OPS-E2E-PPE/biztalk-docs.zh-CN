---
title: 配置验证 （EDIFACT 事务集设置） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81b30a78-3a4b-4827-9b0a-af9ad3e865a3
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6a9ad8f69accd0f479e05e130cc0c28fe874bb86
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233997"
---
# <a name="configuring-validation-edifact-transaction-set-settings"></a><span data-ttu-id="f5939-102">配置验证（EDIFACT--事务集设置）</span><span class="sxs-lookup"><span data-stu-id="f5939-102">Configuring Validation (EDIFACT-Transaction Set Settings)</span></span>
<span data-ttu-id="f5939-103">事务集验证设置定义了 BizTalk Server 验证从某一方收到的事务集的方式。</span><span class="sxs-lookup"><span data-stu-id="f5939-103">The transaction set validation settings define how BizTalk Server validates the transaction sets received from a party.</span></span> <span data-ttu-id="f5939-104">作为验证设置的一部分，您可以指定 BizTalk Server 将对传入交换执行哪种类型的验证</span><span class="sxs-lookup"><span data-stu-id="f5939-104">As part of validation settings you can specify which type of validation BizTalk Server will perform on an incoming interchange</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="f5939-105">没有属性禁用此页上，即使你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="f5939-105">No properties are disabled on this page even if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="f5939-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="f5939-106">Prerequisites</span></span>  
 <span data-ttu-id="f5939-107">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="f5939-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-ack-processing-and-validation-settings"></a><span data-ttu-id="f5939-108">配置确认处理和验证设置</span><span class="sxs-lookup"><span data-stu-id="f5939-108">To configure ACK processing and validation settings</span></span>  
  
1.  <span data-ttu-id="f5939-109">创建 EDIFACT 编码协议中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。</span><span class="sxs-lookup"><span data-stu-id="f5939-109">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="f5939-110">若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="f5939-110">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="f5939-111">单向协议选项卡上，在**事务设置设置**部分中，单击**验证**。</span><span class="sxs-lookup"><span data-stu-id="f5939-111">On a one-way agreement tab, under **Transaction Set Settings** section, click **Validation**.</span></span>  
  
3.  <span data-ttu-id="f5939-112">在网格中，您可以为不同的事务集定义不同的验证设置。</span><span class="sxs-lookup"><span data-stu-id="f5939-112">In the grid, you can define different validation settings for different transaction sets.</span></span> <span data-ttu-id="f5939-113">在**验证**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f5939-113">In the **Validation** page, do the following:</span></span>  
  
    |<span data-ttu-id="f5939-114">使用此选项</span><span class="sxs-lookup"><span data-stu-id="f5939-114">Use this</span></span>|<span data-ttu-id="f5939-115">执行的操作</span><span class="sxs-lookup"><span data-stu-id="f5939-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="f5939-116">**Default**</span><span class="sxs-lookup"><span data-stu-id="f5939-116">**Default**</span></span>|<span data-ttu-id="f5939-117">选中该复选框可定义默认验证设置。</span><span class="sxs-lookup"><span data-stu-id="f5939-117">Select the check box to define a default validation setting.</span></span>|  
    |<span data-ttu-id="f5939-118">**UNH2.1**</span><span class="sxs-lookup"><span data-stu-id="f5939-118">**UNH2.1**</span></span>|<span data-ttu-id="f5939-119">单击此列中的空单元格，并从下拉列表中选择一个事务类型。</span><span class="sxs-lookup"><span data-stu-id="f5939-119">Click the empty cell in the column and from the drop-down select a transaction type.</span></span>|  
    |<span data-ttu-id="f5939-120">**Edi 类型验证**</span><span class="sxs-lookup"><span data-stu-id="f5939-120">**Edi Type Validation**</span></span>|<span data-ttu-id="f5939-121">选择**EDI 类型**来启用对交换收件人的 EDI （数据元素） 验证。</span><span class="sxs-lookup"><span data-stu-id="f5939-121">Select **EDI type** to enable EDI (data element) validation on the interchange receiver.</span></span> <span data-ttu-id="f5939-122">此验证可对事务集数据元素执行 EDI 验证，验证数据类型、长度限制以及空数据元素和尾部分隔符。</span><span class="sxs-lookup"><span data-stu-id="f5939-122">This validation performs EDI validation on transaction-set data elements, validating data types, length restrictions, and empty data elements and training separators.</span></span> <span data-ttu-id="f5939-123">有关详细信息，请参阅[EDI 的类型 （数据元素） 验证](../core/edi-type-data-element-validation.md)。</span><span class="sxs-lookup"><span data-stu-id="f5939-123">For more information, see [EDI Type (Data Element) Validation](../core/edi-type-data-element-validation.md).</span></span> <span data-ttu-id="f5939-124">**注意：** 如果它在中打开的架构批注，即使没有选择此属性，将执行跨-字段/段验证。</span><span class="sxs-lookup"><span data-stu-id="f5939-124">**Note:**  Even if this property is not selected, cross-field/segment validation will be performed if it is turned on in the schema annotation.</span></span>|  
    |<span data-ttu-id="f5939-125">**扩展的验证**</span><span class="sxs-lookup"><span data-stu-id="f5939-125">**Extended validation**</span></span>|<span data-ttu-id="f5939-126">选择此项可让交换发件人发的扩展 (BizTalk XSD) 验证。</span><span class="sxs-lookup"><span data-stu-id="f5939-126">Select this to enable extended (BizTalk XSD) validation of interchanges received from the interchange sender.</span></span> <span data-ttu-id="f5939-127">除了验证 XSD 数据类型之外，这还包括了对字段长度、可选性和重复计数的验证。</span><span class="sxs-lookup"><span data-stu-id="f5939-127">This includes validation of field length, optionality, and repeat count in addition to XSD data type validation.</span></span> <span data-ttu-id="f5939-128">有关详细信息，请参阅[扩展 (BTS XSD) 验证](../core/extended-bts-xsd-validation.md)。</span><span class="sxs-lookup"><span data-stu-id="f5939-128">For more information, see [Extended (BTS-XSD) Validation](../core/extended-bts-xsd-validation.md).</span></span> <span data-ttu-id="f5939-129">**注意：** 可以选择此复选框才**Edi 类型验证**选择。</span><span class="sxs-lookup"><span data-stu-id="f5939-129">**Note:**  You can select this check box only if **Edi Type Validation** is selected.</span></span>|  
    |<span data-ttu-id="f5939-130">**允许前导和尾随零和空间**</span><span class="sxs-lookup"><span data-stu-id="f5939-130">**Allow leading and trailing zeroes and spaces**</span></span>|<span data-ttu-id="f5939-131">选中则指定在 EDI 交换中的数据元素由于前导（或尾随）零或尾随空格而不符合其长度要求，但是将其删除后即符合长度要求的情况下，从参与方接收的 EDI 交换不会验证失败。</span><span class="sxs-lookup"><span data-stu-id="f5939-131">Select to specify that an EDI interchange received from the party will not fail validation if a data element in an EDI interchange does not conform to its length requirement because of leading (or trailing) zeroes or trailing spaces, but does conform to its length requirement when they are removed.</span></span> <span data-ttu-id="f5939-132">**注意：** 可以选择此复选框才**Edi 类型验证**选择。</span><span class="sxs-lookup"><span data-stu-id="f5939-132">**Note:**  You can select this check box only if **Edi Type Validation** is selected.</span></span>|  
    |<span data-ttu-id="f5939-133">**尾随分隔符策略**</span><span class="sxs-lookup"><span data-stu-id="f5939-133">**Trailing Separator Policy**</span></span>|<span data-ttu-id="f5939-134">-选择**不允许**如果不想要允许尾随分隔符，在交换发件人从收到的交换中。</span><span class="sxs-lookup"><span data-stu-id="f5939-134">-   Select **Not Allowed** if you do not want to allow trailing delimiters and separators in an interchange received from the interchange sender.</span></span> <span data-ttu-id="f5939-135">如果该交换包含尾部分隔符，它将被声明无效。</span><span class="sxs-lookup"><span data-stu-id="f5939-135">If the interchange contains trailing delimiters and separators, it will be declared invalid.</span></span><br /><span data-ttu-id="f5939-136">-选择**可选**接受包含或不包含尾随分隔符的交换。</span><span class="sxs-lookup"><span data-stu-id="f5939-136">-   Select **Optional** to accept interchanges with or without trailing delimiters and separators.</span></span><br /><span data-ttu-id="f5939-137">-选择**必需**如果收到的交换必须包含尾随分隔符。</span><span class="sxs-lookup"><span data-stu-id="f5939-137">-   Select **Mandatory** if the received interchange must contain trailing delimiters and separators.</span></span>|  
  
     <span data-ttu-id="f5939-138">您可以根据需要添加许多行，以定义特定交换的验证设置。</span><span class="sxs-lookup"><span data-stu-id="f5939-138">You can add as many rows as you want to define validation settings for specific interchanges.</span></span>  
  
     <span data-ttu-id="f5939-139">若要删除验证设置，选择行，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="f5939-139">To delete a validation setting, select the row and click **Delete**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="f5939-140">在网格中编辑属性可能有些困难。</span><span class="sxs-lookup"><span data-stu-id="f5939-140">Editing the properties in the grid can be a little difficult.</span></span> <span data-ttu-id="f5939-141">相反，你可以选择要编辑，然后编辑中的相同属性的行**编辑所选行**部分。</span><span class="sxs-lookup"><span data-stu-id="f5939-141">Instead, you can select the row to be editing and then edit the same properties in the **Edit Selected Row** section.</span></span> <span data-ttu-id="f5939-142">您在此处提供的设置将反映在所选行中。</span><span class="sxs-lookup"><span data-stu-id="f5939-142">The settings you provide here are reflected in the selected row.</span></span>  
  
4.  <span data-ttu-id="f5939-143">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="f5939-143">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5939-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5939-144">See Also</span></span>  
 [<span data-ttu-id="f5939-145">配置事务集设置 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="f5939-145">Configuring Transaction Set Settings (EDIFACT)</span></span>](../core/configuring-transaction-set-settings-edifact.md)