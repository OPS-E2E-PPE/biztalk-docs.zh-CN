---
title: 配置字符集和分隔符 (EDIFACT) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d4764938-0968-4536-9eb6-d600c03a0428
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d7089cde27eeb45f41852c00122272f506632e61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22234245"
---
# <a name="configuring-charset-and-separators-edifact"></a><span data-ttu-id="81ae3-102">配置字符集和分隔页(EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="81ae3-102">Configuring Charset and Separators (EDIFACT)</span></span>
<span data-ttu-id="81ae3-103">在合作伙伴协议中，您可以指定在为传出 EDIFACT 消息创建信封时 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用哪个字符集 (UNA) 来验证参与方属性。</span><span class="sxs-lookup"><span data-stu-id="81ae3-103">In the partner agreement, you can specify the character set (UNA) that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to validate party properties when creating the envelope for an outgoing EDIFACT message.</span></span> <span data-ttu-id="81ae3-104">你还可以指定哪些分隔符和终止符 (UNB) 用于交换中的段。</span><span class="sxs-lookup"><span data-stu-id="81ae3-104">You can also specify what separators and terminators (UNB) will be used for the segments in the interchange.</span></span>  
  
 <span data-ttu-id="81ae3-105">在 UNA 段中，可定义 BizTalk Server 如何生成它将发送到方的 EDIFACT 编码交换 UNA 段。</span><span class="sxs-lookup"><span data-stu-id="81ae3-105">In the UNA segment, you define how BizTalk Server generates the UNA segment for an EDIFACT-encoded interchange that it sends to the party.</span></span> <span data-ttu-id="81ae3-106">UNA 段定义将用作 EDIFACT 编码的交换的分隔符和指示器的字符。</span><span class="sxs-lookup"><span data-stu-id="81ae3-106">The UNA segment defines the characters that will be used as separators and indicators for an EDIFACT-encoded interchange.</span></span> <span data-ttu-id="81ae3-107">仅当该交换包含非标准的分隔符，请使用此段。</span><span class="sxs-lookup"><span data-stu-id="81ae3-107">Use this segment only if the interchange contains non-standard separator characters.</span></span>  
  
 <span data-ttu-id="81ae3-108">UNB 段中，你可以定义将用于的 EDIFACT 字符集。</span><span class="sxs-lookup"><span data-stu-id="81ae3-108">In the UNB segment, you define the EDIFACT character set to be used.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="81ae3-109">如果你清除了所有属性会被都禁用此页上**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="81ae3-109">All the properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="81ae3-110">仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="81ae3-110">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="81ae3-111">例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="81ae3-111">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="81ae3-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="81ae3-112">Prerequisites</span></span>  
 <span data-ttu-id="81ae3-113">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="81ae3-113">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-character-set-and-separators"></a><span data-ttu-id="81ae3-114">配置字符集和分隔符</span><span class="sxs-lookup"><span data-stu-id="81ae3-114">To configure the character set and separators</span></span>  
  
1.  <span data-ttu-id="81ae3-115">创建 EDIFACT 编码协议中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。</span><span class="sxs-lookup"><span data-stu-id="81ae3-115">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="81ae3-116">若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="81ae3-116">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="81ae3-117">单向协议选项卡上，在**交换设置**部分中，单击**字符集和分隔符**。</span><span class="sxs-lookup"><span data-stu-id="81ae3-117">On a one-way agreement tab, under **Interchange Settings** section, click **Charset and Separators**.</span></span>  
  
3.  <span data-ttu-id="81ae3-118">在**语法 (UNB1)** 部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="81ae3-118">In the **Syntax (UNB1)** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="81ae3-119">有关**标识符 (UNB1.1)**，输入将应用到传出交换的 EDIFACT 字符集。</span><span class="sxs-lookup"><span data-stu-id="81ae3-119">For **Identifier (UNB1.1)**, enter the EDIFACT character set to be applied on the outgoing interchange.</span></span> <span data-ttu-id="81ae3-120">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="81ae3-120">This is a required field.</span></span>  
  
    2.  <span data-ttu-id="81ae3-121">有关**版本 (UNB1.2)**，选择一个介于**1**和**4**。</span><span class="sxs-lookup"><span data-stu-id="81ae3-121">For **Version (UNB1.2)**, select a value between **1** and **4**.</span></span> <span data-ttu-id="81ae3-122">此字段为可选字段。</span><span class="sxs-lookup"><span data-stu-id="81ae3-122">This is an optional field.</span></span>  
  
4.  <span data-ttu-id="81ae3-123">在**分隔符**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="81ae3-123">In the **Separators** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="81ae3-124">有关**组件数据元素分隔符 (UNA1)**，输入组件数据元素分隔符用于分隔复合数据元素中的简单数据元素的值。</span><span class="sxs-lookup"><span data-stu-id="81ae3-124">For **Component data element separator (UNA1)**, enter a value for the component data element separator that separates simple data elements within composite data elements.</span></span> <span data-ttu-id="81ae3-125">选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="81ae3-125">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="81ae3-126">如果你更改其格式，将自动更改您输入的字符。</span><span class="sxs-lookup"><span data-stu-id="81ae3-126">The character you entered will automatically change if you change its format.</span></span>  
  
    2.  <span data-ttu-id="81ae3-127">有关**数据元素分隔符 (UNA2)**，输入数据元素分隔符用于分隔复合数据元素组成两个或多个简单数据元素或不是复合的一部分的简单数据元素的值。</span><span class="sxs-lookup"><span data-stu-id="81ae3-127">For **Data element separator (UNA2)**, enter a value for the data element separator that separates composite data elements consisting of two or more simple data elements or simple data elements that are not part of a composite.</span></span> <span data-ttu-id="81ae3-128">选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="81ae3-128">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="81ae3-129">如果你更改其格式，将自动更改您输入的字符。</span><span class="sxs-lookup"><span data-stu-id="81ae3-129">The character you entered will automatically change if you change its format.</span></span>  
  
    3.  <span data-ttu-id="81ae3-130">有关**十进制表示法 (UNA3)**，选择要在传出交换中使用的十进制表示法。</span><span class="sxs-lookup"><span data-stu-id="81ae3-130">For **Decimal notation (UNA3)**, select the decimal notation to be used in the outgoing interchange.</span></span>  
  
    4.  <span data-ttu-id="81ae3-131">有关**转义指示器 (UNA4)**，指示以下字符不是语法分隔符、 终止符或转义符，而是原始数据的一部分转义指示器输入的值。</span><span class="sxs-lookup"><span data-stu-id="81ae3-131">For **Release indicator (UNA4)**, enter a value for the release indicator that indicates that the following character is not a syntax separator, terminator, or release character, but is part of the original data.</span></span> <span data-ttu-id="81ae3-132">选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="81ae3-132">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="81ae3-133">如果你更改其格式，将自动更改您输入的字符。</span><span class="sxs-lookup"><span data-stu-id="81ae3-133">The character you entered will automatically change if you change its format.</span></span>  
  
    5.  <span data-ttu-id="81ae3-134">有关**重复分隔符 (UNA5)**，输入值的重复分隔符用于分隔事务集内的重复的段。</span><span class="sxs-lookup"><span data-stu-id="81ae3-134">For **Repetition separator (UNA5)**, enter a value for the repetition separator that is used to separate segments that repeat within a transaction set.</span></span> <span data-ttu-id="81ae3-135">选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="81ae3-135">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="81ae3-136">如果你更改其格式，将自动更改您输入的字符。</span><span class="sxs-lookup"><span data-stu-id="81ae3-136">The character you entered will automatically change if you change its format.</span></span>  
  
    6.  <span data-ttu-id="81ae3-137">有关**段终止符 (UNA6)**，为用于指示 EDI 段尾的段终止符输入一个值。</span><span class="sxs-lookup"><span data-stu-id="81ae3-137">For **Segment terminator (UNA6)**, enter a value for the segment terminator that indicates the end of an EDI segment.</span></span>  
  
    7.  <span data-ttu-id="81ae3-138">有关**UNA6 后缀**，选择 BizTalk Server 将使用与段标识符，或者字符**无**， **CR** （回车符）， **LF**（换行符），或**CR LF** （回车符/换行符）。</span><span class="sxs-lookup"><span data-stu-id="81ae3-138">For **UNA6 Suffix**, select the character that BizTalk Server will use with the Segment identifier, either **None**, **CR** (carriage return), **LF** (line feed), or **CR LF** (carriage return/line feed).</span></span> <span data-ttu-id="81ae3-139">如果指定后缀，则段终止符数据元素可以为空。</span><span class="sxs-lookup"><span data-stu-id="81ae3-139">If you designate a suffix, the segment terminator data element can be empty.</span></span> <span data-ttu-id="81ae3-140">如果段终止符留空，则必须指定后缀。</span><span class="sxs-lookup"><span data-stu-id="81ae3-140">If the segment terminator is left empty, you must designate a suffix.</span></span> <span data-ttu-id="81ae3-141">段终止符和后缀的组合可以采用以下任何形式：</span><span class="sxs-lookup"><span data-stu-id="81ae3-141">The combination of the segment terminator and suffix can be any of the following:</span></span>  
  
        -   <span data-ttu-id="81ae3-142">段终止符</span><span class="sxs-lookup"><span data-stu-id="81ae3-142">Segment terminator</span></span>  
  
        -   <span data-ttu-id="81ae3-143">段终止符 + 回车符</span><span class="sxs-lookup"><span data-stu-id="81ae3-143">Segment terminator + carriage return</span></span>  
  
        -   <span data-ttu-id="81ae3-144">段终止符 + 回车符/换行符</span><span class="sxs-lookup"><span data-stu-id="81ae3-144">Segment terminator + carriage return/line feed</span></span>  
  
        -   <span data-ttu-id="81ae3-145">回车符</span><span class="sxs-lookup"><span data-stu-id="81ae3-145">Carriage return</span></span>  
  
        -   <span data-ttu-id="81ae3-146">换行符</span><span class="sxs-lookup"><span data-stu-id="81ae3-146">Line feed</span></span>  
  
        -   <span data-ttu-id="81ae3-147">回车符/换行符</span><span class="sxs-lookup"><span data-stu-id="81ae3-147">Carriage return/line feed</span></span>  
  
5.  <span data-ttu-id="81ae3-148">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**若要验证并接受所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="81ae3-148">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate and accept the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81ae3-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81ae3-149">See Also</span></span>  
 [<span data-ttu-id="81ae3-150">配置交换设置 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="81ae3-150">Configuring Interchange Settings (EDIFACT)</span></span>](../core/configuring-interchange-settings-edifact.md)