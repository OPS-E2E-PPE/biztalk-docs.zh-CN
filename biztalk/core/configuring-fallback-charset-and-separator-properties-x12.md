---
title: 配置回退字符集和分隔符属性 (X12) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 477f4952-6a4e-4e98-a37f-f6e1fe7db3d3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 019fdb4262d778ec8f6605b8f3daef1df7881232
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994534"
---
# <a name="configuring-fallback-charset-and-separator-properties-x12"></a><span data-ttu-id="45dd7-102">配置回退字符集和分隔符属性 (X12)</span><span class="sxs-lookup"><span data-stu-id="45dd7-102">Configuring Fallback Charset and Separator Properties (X12)</span></span>
<span data-ttu-id="45dd7-103">在备用协议中，您可以指定在为传出 X12 消息创建信封时 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用哪个字符集来验证参与方属性。</span><span class="sxs-lookup"><span data-stu-id="45dd7-103">In the fallback agreement, you can specify the character set that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to validate party properties when creating the envelope for an outgoing X12 message.</span></span> <span data-ttu-id="45dd7-104">还可以指定为交换内部的分段使用哪些分隔符和终止符。</span><span class="sxs-lookup"><span data-stu-id="45dd7-104">You can also specify what separators and terminators will be used for the segments in the interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="45dd7-105">此处所述的设置同样适用于 HIPAA 交换。</span><span class="sxs-lookup"><span data-stu-id="45dd7-105">The settings described here also apply to HIPAA interchanges.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="45dd7-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="45dd7-106">Prerequisites</span></span>  
 <span data-ttu-id="45dd7-107">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="45dd7-107">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-character-set-and-separators"></a><span data-ttu-id="45dd7-108">配置字符集和分隔符</span><span class="sxs-lookup"><span data-stu-id="45dd7-108">To configure the character set and separators</span></span>  
  
1. <span data-ttu-id="45dd7-109">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**节点，，然后单击**X12 后备设置**。</span><span class="sxs-lookup"><span data-stu-id="45dd7-109">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click the **Parties** node, and then click **X12 Fallback Settings**.</span></span>  
  
2. <span data-ttu-id="45dd7-110">在中**X12 后备设置**对话框中**X12 协议页**选项卡上，在**交换设置**部分中，单击**字符集和分隔符**.</span><span class="sxs-lookup"><span data-stu-id="45dd7-110">In the **X12 Fallback Settings** dialog box, in the **X12 Agreement Pages** tab, under the **Interchange Settings** section, click **Charset and Separators**.</span></span>  
  
3. <span data-ttu-id="45dd7-111">从**要使用的字符集**下拉列表中，选择 X12 字符集以用于验证为协议输入的属性。</span><span class="sxs-lookup"><span data-stu-id="45dd7-111">From the **Character set to be used** drop-down list, select the X12 character set to be used to validate the properties that you enter for the agreement.</span></span>  
  
   > [!NOTE]
   >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="45dd7-112"> 仅使用此设置来验证为相关协议属性输入的值。</span><span class="sxs-lookup"><span data-stu-id="45dd7-112"> only uses this setting to validate the values entered for the related agreement properties.</span></span> <span data-ttu-id="45dd7-113">在执行运行时处理时，接收管道或发送管道将忽略此字符集属性。</span><span class="sxs-lookup"><span data-stu-id="45dd7-113">The receive pipeline or send pipeline will ignore this character-set property when performing run-time processing.</span></span>  
  
4. <span data-ttu-id="45dd7-114">有关**数据元素**，输入一个字符[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将用于分隔复合数据元素包含两个或多个简单数据元素和不属于复合元素的简单数据元素。</span><span class="sxs-lookup"><span data-stu-id="45dd7-114">For **Data element**, enter a single character that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to separate composite data elements consisting of two or more simple data elements, and simple data elements that are not part of a composite element.</span></span> <span data-ttu-id="45dd7-115">选择**Char**字符数据元素或**Hex**十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="45dd7-115">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="45dd7-116">当您更改的格式时，会自动将更改你输入的字符**Char**到**Hex** ，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="45dd7-116">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
5. <span data-ttu-id="45dd7-117">有关**组件元素分隔符 (ISA16)**，输入一个字符[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将用于分隔复合数据元素中的简单数据元素。</span><span class="sxs-lookup"><span data-stu-id="45dd7-117">For **Component element separator (ISA16)**, enter a single character that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to separate simple data elements within composite data elements.</span></span> <span data-ttu-id="45dd7-118">选择**Char**字符数据元素或**Hex**十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="45dd7-118">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="45dd7-119">当您更改的格式时，会自动将更改你输入的字符**Char**到**Hex** ，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="45dd7-119">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
6. <span data-ttu-id="45dd7-120">有关**段终止符**，输入一个字符[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将用于指示 EDI 段尾。</span><span class="sxs-lookup"><span data-stu-id="45dd7-120">For **Segment terminator**, enter a single character that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use to indicate the end of an EDI segment.</span></span> <span data-ttu-id="45dd7-121">选择**Char**字符数据元素或**Hex**十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="45dd7-121">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="45dd7-122">当您更改的格式时，会自动将更改你输入的字符**Char**到**Hex** ，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="45dd7-122">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
7. <span data-ttu-id="45dd7-123">有关**后缀**，选择的字符的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将使用段标识符，这两个**None**， **CR** （回车符）、 **LF**（换行符），或**CR LF** （回车符/换行符）。</span><span class="sxs-lookup"><span data-stu-id="45dd7-123">For **Suffix**, select the character that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] will use with the Segment identifier, either **None**, **CR** (carriage return), **LF** (line feed), or **CR LF** (carriage return/line feed).</span></span> <span data-ttu-id="45dd7-124">如果指定后缀，则段终止符数据元素可以为空。</span><span class="sxs-lookup"><span data-stu-id="45dd7-124">If you designate a suffix, the segment terminator data element can be empty.</span></span> <span data-ttu-id="45dd7-125">如果段终止符留空，则必须指定后缀。</span><span class="sxs-lookup"><span data-stu-id="45dd7-125">If the segment terminator is left empty, you must designate a suffix.</span></span> <span data-ttu-id="45dd7-126">段终止符和后缀的组合可以采用以下任何形式：</span><span class="sxs-lookup"><span data-stu-id="45dd7-126">The combination of the segment terminator and suffix can be any of the following:</span></span>  
  
   -   <span data-ttu-id="45dd7-127">段终止符</span><span class="sxs-lookup"><span data-stu-id="45dd7-127">Segment terminator</span></span>  
  
   -   <span data-ttu-id="45dd7-128">段终止符 + 回车符</span><span class="sxs-lookup"><span data-stu-id="45dd7-128">Segment terminator + carriage return</span></span>  
  
   -   <span data-ttu-id="45dd7-129">段终止符 + 回车符/换行符</span><span class="sxs-lookup"><span data-stu-id="45dd7-129">Segment terminator + carriage return/line feed</span></span>  
  
   -   <span data-ttu-id="45dd7-130">回车符</span><span class="sxs-lookup"><span data-stu-id="45dd7-130">Carriage return</span></span>  
  
   -   <span data-ttu-id="45dd7-131">换行</span><span class="sxs-lookup"><span data-stu-id="45dd7-131">Line feed</span></span>  
  
   -   <span data-ttu-id="45dd7-132">回车符/换行符</span><span class="sxs-lookup"><span data-stu-id="45dd7-132">Carriage return/line feed</span></span>  
  
8. <span data-ttu-id="45dd7-133">如果负载数据包含还用作数据、 段或组件分隔符的字符，请检查**替换为在通过有效负载中的分隔符**并指定替换字符。</span><span class="sxs-lookup"><span data-stu-id="45dd7-133">If the payload data contains characters that are also used as data, segment, or component separators, check **Replace separators in payload with** and specify a replacement character.</span></span> <span data-ttu-id="45dd7-134">在生成出站 X12 消息时，负载数据中的分隔符的所有实例都将替换为指定字符。</span><span class="sxs-lookup"><span data-stu-id="45dd7-134">When generating the outbound X12 message, all instances of separator characters in the payload data will be replaced with the specified character.</span></span> <span data-ttu-id="45dd7-135">选择**Char**字符数据元素或**Hex**十六进制数据元素。</span><span class="sxs-lookup"><span data-stu-id="45dd7-135">Select **Char** for a character data element or **Hex** for a hexadecimal data element.</span></span> <span data-ttu-id="45dd7-136">当您更改的格式时，会自动将更改你输入的字符**Char**到**Hex** ，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="45dd7-136">The character you entered will automatically change when you change the format from **Char** to **Hex** or vice-versa.</span></span>  
  
9. <span data-ttu-id="45dd7-137">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="45dd7-137">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45dd7-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="45dd7-138">See Also</span></span>  
 [<span data-ttu-id="45dd7-139">为交换处理配置 X12 后备协议属性</span><span class="sxs-lookup"><span data-stu-id="45dd7-139">Configuring X12 Fallback Agreement Properties for Interchange Processing</span></span>](../core/configuring-x12-fallback-agreement-properties-for-interchange-processing.md)