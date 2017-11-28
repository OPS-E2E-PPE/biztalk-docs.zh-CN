---
title: "配置字符集和分隔符 (X12) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6249f2e1-70b0-4960-bbc4-0c3fefd26faa
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 43e32c4d9a240c3302126fc403d64efd787ed54c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-charset-and-separators-x12"></a><span data-ttu-id="ecb35-102">配置字符集和分隔页(X12)</span><span class="sxs-lookup"><span data-stu-id="ecb35-102">Configuring Charset and Separators (X12)</span></span>
<span data-ttu-id="ecb35-103">在合作伙伴协议中，你可以指定在为传出 X12 消息创建信封时 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用哪个字符集来验证参与方属性。</span><span class="sxs-lookup"><span data-stu-id="ecb35-103">In the partner agreement, you can specify the character set that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to validate party properties when creating the envelope for an outgoing X12 message.</span></span> <span data-ttu-id="ecb35-104">还可以指定为交换内部的分段使用哪些分隔符和终止符。</span><span class="sxs-lookup"><span data-stu-id="ecb35-104">You can also specify what separators and terminators will be used for the segments in the interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ecb35-105">此处所述的设置同样适用于 HIPAA 交换。</span><span class="sxs-lookup"><span data-stu-id="ecb35-105">The settings described here also apply to HIPAA interchanges.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ecb35-106">以下属性禁用此页上，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="ecb35-106">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  -   <span data-ttu-id="ecb35-107">**数据元素**</span><span class="sxs-lookup"><span data-stu-id="ecb35-107">**Data element**</span></span>  
> -   <span data-ttu-id="ecb35-108">**组件元素分隔符 (ISA16)**</span><span class="sxs-lookup"><span data-stu-id="ecb35-108">**Component element separator (ISA16)**</span></span>  
> -   <span data-ttu-id="ecb35-109">**段终止符**</span><span class="sxs-lookup"><span data-stu-id="ecb35-109">**Segment terminator**</span></span>  
> -   <span data-ttu-id="ecb35-110">**Suffix**</span><span class="sxs-lookup"><span data-stu-id="ecb35-110">**Suffix**</span></span>  
> -   <span data-ttu-id="ecb35-111">**将负载中的分隔符**</span><span class="sxs-lookup"><span data-stu-id="ecb35-111">**Replace separators in payload with**</span></span>  
>   
>  <span data-ttu-id="ecb35-112">仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="ecb35-112">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="ecb35-113">例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="ecb35-113">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ecb35-114">先决条件</span><span class="sxs-lookup"><span data-stu-id="ecb35-114">Prerequisites</span></span>  
 <span data-ttu-id="ecb35-115">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="ecb35-115">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-character-set-and-separators"></a><span data-ttu-id="ecb35-116">配置字符集和分隔符</span><span class="sxs-lookup"><span data-stu-id="ecb35-116">To configure the character set and separators</span></span>  
  
1.  <span data-ttu-id="ecb35-117">创建 X12 编码协议中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="ecb35-117">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="ecb35-118">若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="ecb35-118">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="ecb35-119">单向协议选项卡上，在**交换设置**部分中，单击**字符集和分隔符**。</span><span class="sxs-lookup"><span data-stu-id="ecb35-119">On a one-way agreement tab, under **Interchange Settings** section, click **Charset and Separators**.</span></span>  
  
3.  <span data-ttu-id="ecb35-120">从**字符将设置为使用**下拉列表中，选择 X12 字符集要用于验证你为协议输入的属性。</span><span class="sxs-lookup"><span data-stu-id="ecb35-120">From the **Character set to be used** drop-down list, select the X12 character set to be used to validate the properties that you enter for the agreement.</span></span>  
  
    > [!NOTE]
    >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="ecb35-121"> 仅使用此设置来验证为相关协议属性输入的值。</span><span class="sxs-lookup"><span data-stu-id="ecb35-121"> only uses this setting to validate the values entered for the related agreement properties.</span></span> <span data-ttu-id="ecb35-122">在执行运行时处理时，接收管道或发送管道将忽略此字符集属性。</span><span class="sxs-lookup"><span data-stu-id="ecb35-122">The receive pipeline or send pipeline will ignore this character-set property when performing run-time processing.</span></span>  
  
4.  <span data-ttu-id="ecb35-123">有关**数据元素**，输入单个字符[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将用于分隔两个或多个简单数据元素和不属于复合元素的简单数据元素组成的复合数据元素。</span><span class="sxs-lookup"><span data-stu-id="ecb35-123">For **Data element**, enter a single character that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to separate composite data elements consisting of two or more simple data elements, and simple data elements that are not part of a composite element.</span></span> <span data-ttu-id="ecb35-124">选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="ecb35-124">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="ecb35-125">在更改中的格式时，您输入的字符将自动更改**Char**到**十六进制**，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="ecb35-125">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
5.  <span data-ttu-id="ecb35-126">有关**组件元素分隔符 (ISA16)**，输入单个字符[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将用于分隔复合数据元素中的简单数据元素。</span><span class="sxs-lookup"><span data-stu-id="ecb35-126">For **Component element separator (ISA16)**, enter a single character that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to separate simple data elements within composite data elements.</span></span> <span data-ttu-id="ecb35-127">选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="ecb35-127">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="ecb35-128">在更改中的格式时，您输入的字符将自动更改**Char**到**十六进制**，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="ecb35-128">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
6.  <span data-ttu-id="ecb35-129">有关**段终止符**，输入单个字符，用于指示 EDI 段尾。</span><span class="sxs-lookup"><span data-stu-id="ecb35-129">For **Segment terminator**, enter a single character to indicate the end of an EDI segment.</span></span> <span data-ttu-id="ecb35-130">选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="ecb35-130">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span>  
  
     <span data-ttu-id="ecb35-131">如果类型为**Char**，默认值是 **~** 。</span><span class="sxs-lookup"><span data-stu-id="ecb35-131">If the type is **Char**, the default value is **~**.</span></span>  
  
     <span data-ttu-id="ecb35-132">如果类型为**十六进制**，默认值是**7E**。</span><span class="sxs-lookup"><span data-stu-id="ecb35-132">If the type is **Hex**, the default value is **7E**.</span></span>  
  
     <span data-ttu-id="ecb35-133">此数据元素是必需的。</span><span class="sxs-lookup"><span data-stu-id="ecb35-133">This data element is required.</span></span>  
  
     <span data-ttu-id="ecb35-134">此元素仅限于 ASCII 字符集中的值。</span><span class="sxs-lookup"><span data-stu-id="ecb35-134">This element is limited to the values in the ASCII character set.</span></span> <span data-ttu-id="ecb35-135">不会根据“常规”页中定义的 X12 字符集对此属性进行验证。</span><span class="sxs-lookup"><span data-stu-id="ecb35-135">This property is not validated against the X12 character set defined in the General page.</span></span>  
  
     <span data-ttu-id="ecb35-136">在更改中的格式时，您输入的字符将自动更改**Char**到**十六进制**，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="ecb35-136">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
7.  <span data-ttu-id="ecb35-137">有关**后缀**，选择要使用的字符**与**段终止符值。</span><span class="sxs-lookup"><span data-stu-id="ecb35-137">For **Suffix**, select the character to use **with** the Segment Terminator value.</span></span> <span data-ttu-id="ecb35-138">选项包括：</span><span class="sxs-lookup"><span data-stu-id="ecb35-138">Options include:</span></span>  
  
    -   <span data-ttu-id="ecb35-139">**无**： 默认</span><span class="sxs-lookup"><span data-stu-id="ecb35-139">**None**: Default</span></span>  
  
    -   <span data-ttu-id="ecb35-140">**CR**： 回车符</span><span class="sxs-lookup"><span data-stu-id="ecb35-140">**CR**: Carriage Return</span></span>  
  
    -   <span data-ttu-id="ecb35-141">**LF**： 换行符</span><span class="sxs-lookup"><span data-stu-id="ecb35-141">**LF**: Line Feed</span></span>  
  
    -   <span data-ttu-id="ecb35-142">**CR LF**： 回车符/换行符源</span><span class="sxs-lookup"><span data-stu-id="ecb35-142">**CR LF**: Carriage Return/Line Feed</span></span>  
  
     <span data-ttu-id="ecb35-143">“段终止符”和“后缀”组合包括：</span><span class="sxs-lookup"><span data-stu-id="ecb35-143">The Segment Terminator and Suffix combinations include the following:</span></span>  
  
    -   <span data-ttu-id="ecb35-144">**任何**段终止符 +**无**后缀</span><span class="sxs-lookup"><span data-stu-id="ecb35-144">**Any** Segment Terminator + **None** Suffix</span></span>  
  
    -   <span data-ttu-id="ecb35-145">**任何**段终止符 + **CR**后缀</span><span class="sxs-lookup"><span data-stu-id="ecb35-145">**Any** Segment Terminator + **CR** Suffix</span></span>  
  
    -   <span data-ttu-id="ecb35-146">**任何**段终止符 + **CR LF**后缀</span><span class="sxs-lookup"><span data-stu-id="ecb35-146">**Any** Segment Terminator + **CR LF** Suffix</span></span>  
  
    -   <span data-ttu-id="ecb35-147">**D （十六进制）**段终止符 +**无**后缀： 这种组合的行为方式好像段终止符为空白，并设置为 CR 的后缀。</span><span class="sxs-lookup"><span data-stu-id="ecb35-147">**D (Hex)** Segment Terminator + **None** Suffix: This combination behaves as if Segment Terminator is blank and Suffix is set to CR.</span></span>  
  
    -   <span data-ttu-id="ecb35-148">（十六进制） 段终止符 +**无**后缀： 这种组合的行为方式好像段终止符保留为空并且后缀设置为 LF。</span><span class="sxs-lookup"><span data-stu-id="ecb35-148">A (Hex) Segment Terminator + **None** Suffix: This combination behaves as if Segment Terminator is blank and Suffix is set to LF.</span></span>  
  
    -   <span data-ttu-id="ecb35-149">**D （十六进制）**段终止符 + **LF**后缀： 这种组合的行为方式好像段终止符是 CR，后缀设置为 LF。</span><span class="sxs-lookup"><span data-stu-id="ecb35-149">**D (Hex)** Segment Terminator + **LF** Suffix: This combination behaves as if Segment Terminator is CR and Suffix is set to LF.</span></span>  
  
8.  <span data-ttu-id="ecb35-150">如果负载数据中的字符也用作数据、 段或组件分隔符，请检查**替换负载中的分隔符**并指定替换字符。</span><span class="sxs-lookup"><span data-stu-id="ecb35-150">If the payload data contains characters that are also used as data, segment, or component separators, check **Replace separators in payload with** and specify a replacement character.</span></span> <span data-ttu-id="ecb35-151">在生成出站 X12 消息时，负载数据中的分隔符的所有实例都将替换为指定字符。</span><span class="sxs-lookup"><span data-stu-id="ecb35-151">When generating the outbound X12 message, all instances of separator characters in the payload data will be replaced with the specified character.</span></span> <span data-ttu-id="ecb35-152">选择**Char**为字符数据元素或**十六进制**为十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="ecb35-152">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="ecb35-153">在更改中的格式时，您输入的字符将自动更改**Char**到**十六进制**，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="ecb35-153">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
9. <span data-ttu-id="ecb35-154">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="ecb35-154">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecb35-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ecb35-155">See Also</span></span>  
 [<span data-ttu-id="ecb35-156">配置交换设置 (X12)</span><span class="sxs-lookup"><span data-stu-id="ecb35-156">Configuring Interchange Settings (X12)</span></span>](../core/configuring-interchange-settings-x12.md)