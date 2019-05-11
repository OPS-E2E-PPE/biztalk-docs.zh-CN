---
title: 配置字符集和分隔符 (EDIFACT) |Microsoft Docs
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
ms.openlocfilehash: fba6b6f3c45692bd377f676f4be0633beed7e018
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356187"
---
# <a name="configuring-charset-and-separators-edifact"></a><span data-ttu-id="8ea2b-102">配置字符集和分隔符 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="8ea2b-102">Configuring Charset and Separators (EDIFACT)</span></span>
<span data-ttu-id="8ea2b-103">在合作伙伴协议中，您可以指定字符集 (UNA)[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将用于创建为传出 EDIFACT 消息信封时验证参与方属性。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-103">In the partner agreement, you can specify the character set (UNA) that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to validate party properties when creating the envelope for an outgoing EDIFACT message.</span></span> <span data-ttu-id="8ea2b-104">此外可以指定将交换中的分段使用哪些分隔符和终止符 (UNB)。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-104">You can also specify what separators and terminators (UNB) will be used for the segments in the interchange.</span></span>  
  
 <span data-ttu-id="8ea2b-105">在 UNA 段中，可以定义 BizTalk Server 如何生成它发送到参与方的 EDIFACT 编码交换的 UNA 段。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-105">In the UNA segment, you define how BizTalk Server generates the UNA segment for an EDIFACT-encoded interchange that it sends to the party.</span></span> <span data-ttu-id="8ea2b-106">UNA 段定义将用作分隔符和指示器的 EDIFACT 编码交换的字符。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-106">The UNA segment defines the characters that will be used as separators and indicators for an EDIFACT-encoded interchange.</span></span> <span data-ttu-id="8ea2b-107">使用此段，仅当该交换包含非标准分隔符字符。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-107">Use this segment only if the interchange contains non-standard separator characters.</span></span>  
  
 <span data-ttu-id="8ea2b-108">在 UNB 段定义将设置为使用的 EDIFACT 字符集。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-108">In the UNB segment, you define the EDIFACT character set to be used.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="8ea2b-109">如果你清除了所有属性会都禁用此页上**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-109">All the properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="8ea2b-110">仅在与参与方所发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-110">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="8ea2b-111">例如，如果创建两个参与方 Party A 和参与方 B，并且对于参与方 A 清除该复选框，上述列表中的属性上禁用**参与方 A-> 参与方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-111">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8ea2b-112">先决条件</span><span class="sxs-lookup"><span data-stu-id="8ea2b-112">Prerequisites</span></span>  
 <span data-ttu-id="8ea2b-113">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-113">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-character-set-and-separators"></a><span data-ttu-id="8ea2b-114">若要配置字符集和分隔符</span><span class="sxs-lookup"><span data-stu-id="8ea2b-114">To configure the character set and separators</span></span>  
  
1.  <span data-ttu-id="8ea2b-115">创建 EDIFACT 编码协议，如中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-115">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="8ea2b-116">若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-116">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="8ea2b-117">在单向协议选项卡下**交换设置**部分中，单击**字符集和分隔符**。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-117">On a one-way agreement tab, under **Interchange Settings** section, click **Charset and Separators**.</span></span>  
  
3.  <span data-ttu-id="8ea2b-118">在中**语法 (UNB1)** 部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8ea2b-118">In the **Syntax (UNB1)** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="8ea2b-119">有关**标识符 (UNB1.1)**，为要应用于传出交换的 EDIFACT 字符集输入。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-119">For **Identifier (UNB1.1)**, enter the EDIFACT character set to be applied on the outgoing interchange.</span></span> <span data-ttu-id="8ea2b-120">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-120">This is a required field.</span></span>  
  
    2.  <span data-ttu-id="8ea2b-121">有关**版本 (UNB1.2)**，选择介于**1**并**4**。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-121">For **Version (UNB1.2)**, select a value between **1** and **4**.</span></span> <span data-ttu-id="8ea2b-122">这是一个可选字段。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-122">This is an optional field.</span></span>  
  
4.  <span data-ttu-id="8ea2b-123">在中**分隔符**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8ea2b-123">In the **Separators** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="8ea2b-124">有关**组件数据元素分隔符 (UNA1)**，输入组件数据元素分隔符用于分隔复合数据元素中的简单数据元素的值。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-124">For **Component data element separator (UNA1)**, enter a value for the component data element separator that separates simple data elements within composite data elements.</span></span> <span data-ttu-id="8ea2b-125">选择**Char**字符数据元素或**Hex**十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-125">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="8ea2b-126">如果更改其格式，你输入的字符将自动更改。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-126">The character you entered will automatically change if you change its format.</span></span>  
  
    2.  <span data-ttu-id="8ea2b-127">有关**数据元素分隔符 (UNA2)**，分隔复合数据元素包含两个或多个简单数据元素或简单数据元素不属于复合数据元素分隔符输入一个值。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-127">For **Data element separator (UNA2)**, enter a value for the data element separator that separates composite data elements consisting of two or more simple data elements or simple data elements that are not part of a composite.</span></span> <span data-ttu-id="8ea2b-128">选择**Char**字符数据元素或**Hex**十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-128">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="8ea2b-129">如果更改其格式，你输入的字符将自动更改。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-129">The character you entered will automatically change if you change its format.</span></span>  
  
    3.  <span data-ttu-id="8ea2b-130">有关**十进制符号 (UNA3)**，选择要在传出交换中使用的十进制表示法。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-130">For **Decimal notation (UNA3)**, select the decimal notation to be used in the outgoing interchange.</span></span>  
  
    4.  <span data-ttu-id="8ea2b-131">有关**转义指示器 (UNA4)**，输入转义指示器用于指示后面的字符不是语法分隔符、 终止符或转义符，而是原始数据的一部分的值。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-131">For **Release indicator (UNA4)**, enter a value for the release indicator that indicates that the following character is not a syntax separator, terminator, or release character, but is part of the original data.</span></span> <span data-ttu-id="8ea2b-132">选择**Char**字符数据元素或**Hex**十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-132">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="8ea2b-133">如果更改其格式，你输入的字符将自动更改。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-133">The character you entered will automatically change if you change its format.</span></span>  
  
    5.  <span data-ttu-id="8ea2b-134">有关**重复分隔符 (UNA5)**，为此重复分隔符用于分隔事务集内的重复的段输入一个值。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-134">For **Repetition separator (UNA5)**, enter a value for the repetition separator that is used to separate segments that repeat within a transaction set.</span></span> <span data-ttu-id="8ea2b-135">选择**Char**字符数据元素或**Hex**十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-135">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="8ea2b-136">如果更改其格式，你输入的字符将自动更改。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-136">The character you entered will automatically change if you change its format.</span></span>  
  
    6.  <span data-ttu-id="8ea2b-137">有关**段终止符 (UNA6)**，用于指示 EDI 段尾段终止符输入的值。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-137">For **Segment terminator (UNA6)**, enter a value for the segment terminator that indicates the end of an EDI segment.</span></span>  
  
    7.  <span data-ttu-id="8ea2b-138">有关**UNA6 后缀**，选择 BizTalk Server 将与段标识符，或者使用的字符**None**， **CR** （回车符）、 **LF**（换行符），或**CR LF** （回车符/换行符）。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-138">For **UNA6 Suffix**, select the character that BizTalk Server will use with the Segment identifier, either **None**, **CR** (carriage return), **LF** (line feed), or **CR LF** (carriage return/line feed).</span></span> <span data-ttu-id="8ea2b-139">如果指定了后缀，则段终止符数据元素可以为空。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-139">If you designate a suffix, the segment terminator data element can be empty.</span></span> <span data-ttu-id="8ea2b-140">如果段终止符留空，则必须指定后缀。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-140">If the segment terminator is left empty, you must designate a suffix.</span></span> <span data-ttu-id="8ea2b-141">段终止符和后缀的组合可以是以下任一项：</span><span class="sxs-lookup"><span data-stu-id="8ea2b-141">The combination of the segment terminator and suffix can be any of the following:</span></span>  
  
        -   <span data-ttu-id="8ea2b-142">段终止符</span><span class="sxs-lookup"><span data-stu-id="8ea2b-142">Segment terminator</span></span>  
  
        -   <span data-ttu-id="8ea2b-143">段终止符 + 回车符</span><span class="sxs-lookup"><span data-stu-id="8ea2b-143">Segment terminator + carriage return</span></span>  
  
        -   <span data-ttu-id="8ea2b-144">段终止符 + 回车符/换行符</span><span class="sxs-lookup"><span data-stu-id="8ea2b-144">Segment terminator + carriage return/line feed</span></span>  
  
        -   <span data-ttu-id="8ea2b-145">回车符</span><span class="sxs-lookup"><span data-stu-id="8ea2b-145">Carriage return</span></span>  
  
        -   <span data-ttu-id="8ea2b-146">换行</span><span class="sxs-lookup"><span data-stu-id="8ea2b-146">Line feed</span></span>  
  
        -   <span data-ttu-id="8ea2b-147">回车符/换行符</span><span class="sxs-lookup"><span data-stu-id="8ea2b-147">Carriage return/line feed</span></span>  
  
5.  <span data-ttu-id="8ea2b-148">单击**Apply**接受所做的更改，然后才能继续进行配置，或单击**确定**以验证并接受所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="8ea2b-148">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate and accept the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ea2b-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="8ea2b-149">See Also</span></span>  
 [<span data-ttu-id="8ea2b-150">配置交换设置 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="8ea2b-150">Configuring Interchange Settings (EDIFACT)</span></span>](../core/configuring-interchange-settings-edifact.md)