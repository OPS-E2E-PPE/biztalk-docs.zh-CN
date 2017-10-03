---
title: "配置回退字符集和分隔符属性 (EDIFACT) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9eadc9c1-ebec-42f5-a9ca-06cb28bebcdf
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0b517a98130f2d245d68083dc16c65865950800c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-fallback-charset-and-separator-properties-edifact"></a><span data-ttu-id="a938f-102">配置回退字符集和分隔符属性 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="a938f-102">Configuring Fallback Charset and Separator Properties (EDIFACT)</span></span>
<span data-ttu-id="a938f-103">在回滚协议中，您可以指定在为传出 EDIFACT 消息创建信封时 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用哪个字符集 (UNMA) 来验证参与方属性。</span><span class="sxs-lookup"><span data-stu-id="a938f-103">In the fallback agreement, you can specify the character set (UNA) that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to validate party properties when creating the envelope for an outgoing EDIFACT message.</span></span> <span data-ttu-id="a938f-104">你还可以指定哪些分隔符和终止符 (UNB) 用于交换中的段。</span><span class="sxs-lookup"><span data-stu-id="a938f-104">You can also specify what separators and terminators (UNB) will be used for the segments in the interchange.</span></span>  
  
 <span data-ttu-id="a938f-105">在 UNA 段中，可定义 BizTalk Server 如何生成它将发送到方的 EDIFACT 编码交换 UNA 段。</span><span class="sxs-lookup"><span data-stu-id="a938f-105">In the UNA segment, you define how BizTalk Server generates the UNA segment for an EDIFACT-encoded interchange that it sends to the party.</span></span> <span data-ttu-id="a938f-106">UNA 段定义将用作 EDIFACT 编码的交换的分隔符和指示器的字符。</span><span class="sxs-lookup"><span data-stu-id="a938f-106">The UNA segment defines the characters that will be used as separators and indicators for an EDIFACT-encoded interchange.</span></span> <span data-ttu-id="a938f-107">仅当该交换包含非标准的分隔符，请使用此段。</span><span class="sxs-lookup"><span data-stu-id="a938f-107">Use this segment only if the interchange contains non-standard separator characters.</span></span>  
  
 <span data-ttu-id="a938f-108">UNB 段中，你可以定义将用于的 EDIFACT 字符集。</span><span class="sxs-lookup"><span data-stu-id="a938f-108">In the UNB segment, you define the EDIFACT character set to be used.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a938f-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="a938f-109">Prerequisites</span></span>  
 <span data-ttu-id="a938f-110">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="a938f-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-character-set-and-separators"></a><span data-ttu-id="a938f-111">配置字符集和分隔符</span><span class="sxs-lookup"><span data-stu-id="a938f-111">To configure the character set and separators</span></span>  
  
1.  <span data-ttu-id="a938f-112">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**EDIFACT 回退设置**。</span><span class="sxs-lookup"><span data-stu-id="a938f-112">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **EDIFACT Fallback Settings**.</span></span>  
  
2.  <span data-ttu-id="a938f-113">在**EDIFACT 回退设置**对话框中，在**EDIFACT 协议页**选项卡上，在**交换设置**部分中，单击**Charset 和分隔符**。</span><span class="sxs-lookup"><span data-stu-id="a938f-113">In the **EDIFACT Fallback Settings** dialog box, in the **EDIFACT Agreement Pages** tab, under the **Interchange Settings** section, click **Charset and Separators**.</span></span>  
  
3.  <span data-ttu-id="a938f-114">在**语法 (UNB1)**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a938f-114">In the **Syntax (UNB1)** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="a938f-115">有关**标识符 (UNB1.1)**，输入将应用到传出交换的 EDIFACT 字符集。</span><span class="sxs-lookup"><span data-stu-id="a938f-115">For **Identifier (UNB1.1)**, enter the EDIFACT character set to be applied on the outgoing interchange.</span></span> <span data-ttu-id="a938f-116">这是必填字段。</span><span class="sxs-lookup"><span data-stu-id="a938f-116">This is a required field.</span></span>  
  
    2.  <span data-ttu-id="a938f-117">有关**版本 (UNB1.2)**，选择一个介于**1**和**4**。</span><span class="sxs-lookup"><span data-stu-id="a938f-117">For **Version (UNB1.2)**, select a value between **1** and **4**.</span></span> <span data-ttu-id="a938f-118">此字段为可选字段。</span><span class="sxs-lookup"><span data-stu-id="a938f-118">This is an optional field.</span></span>  
  
4.  <span data-ttu-id="a938f-119">在**分隔符**部分中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a938f-119">In the **Separators** section, do the following:</span></span>  
  
    1.  <span data-ttu-id="a938f-120">有关**组件数据元素分隔符 (UNA1)**，输入组件数据元素分隔符用于分隔复合数据元素中的简单数据元素的值。</span><span class="sxs-lookup"><span data-stu-id="a938f-120">For **Component data element separator (UNA1)**, enter a value for the component data element separator that separates simple data elements within composite data elements.</span></span> <span data-ttu-id="a938f-121">选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="a938f-121">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="a938f-122">如果你更改其格式，将自动更改您输入的字符。</span><span class="sxs-lookup"><span data-stu-id="a938f-122">The character you entered will automatically change if you change its format.</span></span>  
  
    2.  <span data-ttu-id="a938f-123">有关**数据元素分隔符 (UNA2)**，输入数据元素分隔符用于分隔复合数据元素组成两个或多个简单数据元素或不是复合的一部分的简单数据元素的值。</span><span class="sxs-lookup"><span data-stu-id="a938f-123">For **Data element separator (UNA2)**, enter a value for the data element separator that separates composite data elements consisting of two or more simple data elements or simple data elements that are not part of a composite.</span></span> <span data-ttu-id="a938f-124">选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="a938f-124">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="a938f-125">如果你更改其格式，将自动更改您输入的字符。</span><span class="sxs-lookup"><span data-stu-id="a938f-125">The character you entered will automatically change if you change its format.</span></span>  
  
    3.  <span data-ttu-id="a938f-126">有关**十进制表示法 (UNA3)**，选择要在传出交换中使用的十进制表示法。</span><span class="sxs-lookup"><span data-stu-id="a938f-126">For **Decimal notation (UNA3)**, select the decimal notation to be used in the outgoing interchange.</span></span>  
  
    4.  <span data-ttu-id="a938f-127">有关**转义指示器 (UNA4)**，指示以下字符不是语法分隔符、 终止符或转义符，而是原始数据的一部分转义指示器输入的值。</span><span class="sxs-lookup"><span data-stu-id="a938f-127">For **Release indicator (UNA4)**, enter a value for the release indicator that indicates that the following character is not a syntax separator, terminator, or release character, but is part of the original data.</span></span> <span data-ttu-id="a938f-128">选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="a938f-128">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="a938f-129">如果你更改其格式，将自动更改您输入的字符。</span><span class="sxs-lookup"><span data-stu-id="a938f-129">The character you entered will automatically change if you change its format.</span></span>  
  
    5.  <span data-ttu-id="a938f-130">有关**重复分隔符 (UNA5)**，输入值的重复分隔符用于分隔事务集内的重复的段。</span><span class="sxs-lookup"><span data-stu-id="a938f-130">For **Repetition separator (UNA5)**, enter a value for the repetition separator that is used to separate segments that repeat within a transaction set.</span></span> <span data-ttu-id="a938f-131">选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="a938f-131">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="a938f-132">如果你更改其格式，将自动更改您输入的字符。</span><span class="sxs-lookup"><span data-stu-id="a938f-132">The character you entered will automatically change if you change its format.</span></span>  
  
    6.  <span data-ttu-id="a938f-133">有关**段终止符 (UNA6)**，为用于指示 EDI 段尾的段终止符输入一个值。</span><span class="sxs-lookup"><span data-stu-id="a938f-133">For **Segment terminator (UNA6)**, enter a value for the segment terminator that indicates the end of an EDI segment.</span></span>  
  
    7.  <span data-ttu-id="a938f-134">有关**UNA6 后缀**，选择 BizTalk Server 将使用与段标识符，或者字符**无**， **CR** （回车符）， **LF**（换行符），或**CR LF** （回车符/换行符）。</span><span class="sxs-lookup"><span data-stu-id="a938f-134">For **UNA6 Suffix**, select the character that BizTalk Server will use with the Segment identifier, either **None**, **CR** (carriage return), **LF** (line feed), or **CR LF** (carriage return/line feed).</span></span> <span data-ttu-id="a938f-135">如果指定后缀，则段终止符数据元素可以为空。</span><span class="sxs-lookup"><span data-stu-id="a938f-135">If you designate a suffix, the segment terminator data element can be empty.</span></span> <span data-ttu-id="a938f-136">如果段终止符留空，则必须指定后缀。</span><span class="sxs-lookup"><span data-stu-id="a938f-136">If the segment terminator is left empty, you must designate a suffix.</span></span> <span data-ttu-id="a938f-137">段终止符和后缀的组合可以采用以下任何形式：</span><span class="sxs-lookup"><span data-stu-id="a938f-137">The combination of the segment terminator and suffix can be any of the following:</span></span>  
  
        -   <span data-ttu-id="a938f-138">段终止符</span><span class="sxs-lookup"><span data-stu-id="a938f-138">Segment terminator</span></span>  
  
        -   <span data-ttu-id="a938f-139">段终止符 + 回车符</span><span class="sxs-lookup"><span data-stu-id="a938f-139">Segment terminator + carriage return</span></span>  
  
        -   <span data-ttu-id="a938f-140">段终止符 + 回车符/换行符</span><span class="sxs-lookup"><span data-stu-id="a938f-140">Segment terminator + carriage return/line feed</span></span>  
  
        -   <span data-ttu-id="a938f-141">回车符</span><span class="sxs-lookup"><span data-stu-id="a938f-141">Carriage return</span></span>  
  
        -   <span data-ttu-id="a938f-142">换行符</span><span class="sxs-lookup"><span data-stu-id="a938f-142">Line feed</span></span>  
  
        -   <span data-ttu-id="a938f-143">回车符/换行符</span><span class="sxs-lookup"><span data-stu-id="a938f-143">Carriage return/line feed</span></span>  
  
5.  <span data-ttu-id="a938f-144">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**若要验证并接受所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="a938f-144">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate and accept the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a938f-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a938f-145">See Also</span></span>  
 [<span data-ttu-id="a938f-146">为交换处理配置 EDIFACT 回退协议属性</span><span class="sxs-lookup"><span data-stu-id="a938f-146">Configuring EDIFACT Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-edifact-fallback-agreement-properties-for-interchange-processing.md)