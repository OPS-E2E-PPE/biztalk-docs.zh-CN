---
title: 配置字符集和分隔符 (X12) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6249f2e1-70b0-4960-bbc4-0c3fefd26faa
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 108c539ec93d997410062dcaf4737cb4f213f911
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356145"
---
# <a name="configuring-charset-and-separators-x12"></a><span data-ttu-id="d338e-102">配置字符集和分隔页(X12)</span><span class="sxs-lookup"><span data-stu-id="d338e-102">Configuring Charset and Separators (X12)</span></span>
<span data-ttu-id="d338e-103">在合作伙伴协议中，您可以指定的字符集[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将用于验证参与方属性创建为传出 x12 信封时消息。</span><span class="sxs-lookup"><span data-stu-id="d338e-103">In the partner agreement, you can specify the character set that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to validate party properties when creating the envelope for an outgoing X12 message.</span></span> <span data-ttu-id="d338e-104">此外可以指定将交换中的分段使用哪些分隔符和终止符。</span><span class="sxs-lookup"><span data-stu-id="d338e-104">You can also specify what separators and terminators will be used for the segments in the interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d338e-105">此处所述的设置也适用于 HIPAA 交换。</span><span class="sxs-lookup"><span data-stu-id="d338e-105">The settings described here also apply to HIPAA interchanges.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="d338e-106">以下属性禁用此页上，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="d338e-106">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
> 
> - <span data-ttu-id="d338e-107">**数据元素**</span><span class="sxs-lookup"><span data-stu-id="d338e-107">**Data element**</span></span>  
>   -   <span data-ttu-id="d338e-108">**组件元素分隔符 (ISA16)**</span><span class="sxs-lookup"><span data-stu-id="d338e-108">**Component element separator (ISA16)**</span></span>  
>   -   <span data-ttu-id="d338e-109">**段终止符**</span><span class="sxs-lookup"><span data-stu-id="d338e-109">**Segment terminator**</span></span>  
>   -   <span data-ttu-id="d338e-110">**Suffix**</span><span class="sxs-lookup"><span data-stu-id="d338e-110">**Suffix**</span></span>  
>   -   <span data-ttu-id="d338e-111">**替换负载中的分隔符**</span><span class="sxs-lookup"><span data-stu-id="d338e-111">**Replace separators in payload with**</span></span>  
> 
>   <span data-ttu-id="d338e-112">仅在与参与方所发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="d338e-112">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="d338e-113">例如，如果创建两个参与方 Party A 和参与方 B，并且对于参与方 A 清除该复选框，上述列表中的属性上禁用**参与方 A-> 参与方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="d338e-113">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d338e-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="d338e-114">Prerequisites</span></span>  
 <span data-ttu-id="d338e-115">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="d338e-115">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-character-set-and-separators"></a><span data-ttu-id="d338e-116">若要配置字符集和分隔符</span><span class="sxs-lookup"><span data-stu-id="d338e-116">To configure the character set and separators</span></span>  
  
1. <span data-ttu-id="d338e-117">创建 X12 编码协议，如中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="d338e-117">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="d338e-118">若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="d338e-118">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2. <span data-ttu-id="d338e-119">在单向协议选项卡下**交换设置**部分中，单击**字符集和分隔符**。</span><span class="sxs-lookup"><span data-stu-id="d338e-119">On a one-way agreement tab, under **Interchange Settings** section, click **Charset and Separators**.</span></span>  
  
3. <span data-ttu-id="d338e-120">从**要使用的字符集**下拉列表中，选择 X12 字符集以用于验证为协议输入的属性。</span><span class="sxs-lookup"><span data-stu-id="d338e-120">From the **Character set to be used** drop-down list, select the X12 character set to be used to validate the properties that you enter for the agreement.</span></span>  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="d338e-121">仅使用此设置验证为相关的协议属性输入的值。</span><span class="sxs-lookup"><span data-stu-id="d338e-121">only uses this setting to validate the values entered for the related agreement properties.</span></span> <span data-ttu-id="d338e-122">执行运行时处理时，接收管道或发送管道将忽略此字符集属性。</span><span class="sxs-lookup"><span data-stu-id="d338e-122">The receive pipeline or send pipeline will ignore this character-set property when performing run-time processing.</span></span>  
  
4. <span data-ttu-id="d338e-123">有关**数据元素**，输入一个字符[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将用于分隔复合数据元素包含两个或多个简单数据元素和不属于复合元素的简单数据元素。</span><span class="sxs-lookup"><span data-stu-id="d338e-123">For **Data element**, enter a single character that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to separate composite data elements consisting of two or more simple data elements, and simple data elements that are not part of a composite element.</span></span> <span data-ttu-id="d338e-124">选择**Char**字符数据元素或**Hex**十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="d338e-124">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="d338e-125">当您更改的格式时，会自动将更改你输入的字符**Char**到**Hex** ，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="d338e-125">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
5. <span data-ttu-id="d338e-126">有关**组件元素分隔符 (ISA16)**，输入一个字符[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将用于分隔复合数据元素中的简单数据元素。</span><span class="sxs-lookup"><span data-stu-id="d338e-126">For **Component element separator (ISA16)**, enter a single character that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to separate simple data elements within composite data elements.</span></span> <span data-ttu-id="d338e-127">选择**Char**字符数据元素或**Hex**十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="d338e-127">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="d338e-128">当您更改的格式时，会自动将更改你输入的字符**Char**到**Hex** ，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="d338e-128">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
6. <span data-ttu-id="d338e-129">有关**段终止符**，输入单个字符，用于指示 EDI 段尾。</span><span class="sxs-lookup"><span data-stu-id="d338e-129">For **Segment terminator**, enter a single character to indicate the end of an EDI segment.</span></span> <span data-ttu-id="d338e-130">选择**Char**字符数据元素或**Hex**十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="d338e-130">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span>  
  
    <span data-ttu-id="d338e-131">如果类型为**Char**，默认值是**~**。</span><span class="sxs-lookup"><span data-stu-id="d338e-131">If the type is **Char**, the default value is **~**.</span></span>  
  
    <span data-ttu-id="d338e-132">如果类型为**十六进制**，默认值是**7E**。</span><span class="sxs-lookup"><span data-stu-id="d338e-132">If the type is **Hex**, the default value is **7E**.</span></span>  
  
    <span data-ttu-id="d338e-133">此数据元素是必需的。</span><span class="sxs-lookup"><span data-stu-id="d338e-133">This data element is required.</span></span>  
  
    <span data-ttu-id="d338e-134">此元素仅限于 ASCII 字符集中的值。</span><span class="sxs-lookup"><span data-stu-id="d338e-134">This element is limited to the values in the ASCII character set.</span></span> <span data-ttu-id="d338e-135">根据 X12 不验证此属性在常规页中定义的字符集。</span><span class="sxs-lookup"><span data-stu-id="d338e-135">This property is not validated against the X12 character set defined in the General page.</span></span>  
  
    <span data-ttu-id="d338e-136">当您更改的格式时，会自动将更改你输入的字符**Char**到**Hex** ，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="d338e-136">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
7. <span data-ttu-id="d338e-137">有关**后缀**，选择要使用的字符**与**段终止符值。</span><span class="sxs-lookup"><span data-stu-id="d338e-137">For **Suffix**, select the character to use **with** the Segment Terminator value.</span></span> <span data-ttu-id="d338e-138">选项包括：</span><span class="sxs-lookup"><span data-stu-id="d338e-138">Options include:</span></span>  
  
   - <span data-ttu-id="d338e-139">**无**：默认</span><span class="sxs-lookup"><span data-stu-id="d338e-139">**None**: Default</span></span>  
  
   - <span data-ttu-id="d338e-140">**CR**:回车</span><span class="sxs-lookup"><span data-stu-id="d338e-140">**CR**: Carriage Return</span></span>  
  
   - <span data-ttu-id="d338e-141">**LF**:换行</span><span class="sxs-lookup"><span data-stu-id="d338e-141">**LF**: Line Feed</span></span>  
  
   - <span data-ttu-id="d338e-142">**CR LF**:回车符/换行符源</span><span class="sxs-lookup"><span data-stu-id="d338e-142">**CR LF**: Carriage Return/Line Feed</span></span>  
  
     <span data-ttu-id="d338e-143">段终止符和后缀组合包括：</span><span class="sxs-lookup"><span data-stu-id="d338e-143">The Segment Terminator and Suffix combinations include the following:</span></span>  
  
   - <span data-ttu-id="d338e-144">**任何**段终止符 + **None**后缀</span><span class="sxs-lookup"><span data-stu-id="d338e-144">**Any** Segment Terminator + **None** Suffix</span></span>  
  
   - <span data-ttu-id="d338e-145">**任何**段终止符 + **CR**后缀</span><span class="sxs-lookup"><span data-stu-id="d338e-145">**Any** Segment Terminator + **CR** Suffix</span></span>  
  
   - <span data-ttu-id="d338e-146">**任何**段终止符 + **CR LF**后缀</span><span class="sxs-lookup"><span data-stu-id="d338e-146">**Any** Segment Terminator + **CR LF** Suffix</span></span>  
  
   - <span data-ttu-id="d338e-147">**D （十六进制）** 段终止符 + **None**后缀：此组合行为就像段终止符为空且后缀设置为 CR。</span><span class="sxs-lookup"><span data-stu-id="d338e-147">**D (Hex)** Segment Terminator + **None** Suffix: This combination behaves as if Segment Terminator is blank and Suffix is set to CR.</span></span>  
  
   - <span data-ttu-id="d338e-148">（十六进制） 段终止符 + **None**后缀：此组合行为就像段终止符为空且后缀设置为 LF。</span><span class="sxs-lookup"><span data-stu-id="d338e-148">A (Hex) Segment Terminator + **None** Suffix: This combination behaves as if Segment Terminator is blank and Suffix is set to LF.</span></span>  
  
   - <span data-ttu-id="d338e-149">**D （十六进制）** 段终止符 + **LF**后缀：此组合行为就像段终止符为 CR 且后缀设置为 LF。</span><span class="sxs-lookup"><span data-stu-id="d338e-149">**D (Hex)** Segment Terminator + **LF** Suffix: This combination behaves as if Segment Terminator is CR and Suffix is set to LF.</span></span>  
  
8. <span data-ttu-id="d338e-150">如果负载数据包含还用作数据、 段或组件分隔符的字符，请检查**替换为在通过有效负载中的分隔符**并指定替换字符。</span><span class="sxs-lookup"><span data-stu-id="d338e-150">If the payload data contains characters that are also used as data, segment, or component separators, check **Replace separators in payload with** and specify a replacement character.</span></span> <span data-ttu-id="d338e-151">生成出站 X12 消息时，数据将替换为指定的字符的有效负载中分隔符的所有实例。</span><span class="sxs-lookup"><span data-stu-id="d338e-151">When generating the outbound X12 message, all instances of separator characters in the payload data will be replaced with the specified character.</span></span> <span data-ttu-id="d338e-152">选择**Char**字符数据元素或**Hex**十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="d338e-152">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="d338e-153">当您更改的格式时，会自动将更改你输入的字符**Char**到**Hex** ，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="d338e-153">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
9. <span data-ttu-id="d338e-154">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="d338e-154">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d338e-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="d338e-155">See Also</span></span>  
 [<span data-ttu-id="d338e-156">配置交换设置 (X12)</span><span class="sxs-lookup"><span data-stu-id="d338e-156">Configuring Interchange Settings (X12)</span></span>](../core/configuring-interchange-settings-x12.md)