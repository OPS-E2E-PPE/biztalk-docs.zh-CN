---
title: 配置信封 （EDIFACT 交换设置） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 501ccc5f-e21c-4c36-9509-217d5b3ba21f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 531b559e690fae5369298a90cd372edcae79db57
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22233517"
---
# <a name="configuring-envelopes-edifact-interchange-settings"></a><span data-ttu-id="79ad6-102">配置信封（EDIFACT-交换设置）</span><span class="sxs-lookup"><span data-stu-id="79ad6-102">Configuring Envelopes (EDIFACT-Interchange Settings)</span></span>
<span data-ttu-id="79ad6-103">本节提供有关如何配置 EDIFACT 待发邮件的信封的说明。</span><span class="sxs-lookup"><span data-stu-id="79ad6-103">This section provides instructions on how to configure the envelope for outgoing EDIFACT messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="79ad6-104">如果你清除了所有属性会被都禁用此页上**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="79ad6-104">All the properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="79ad6-105">仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="79ad6-105">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="79ad6-106">例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="79ad6-106">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="79ad6-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="79ad6-107">Prerequisites</span></span>  
 <span data-ttu-id="79ad6-108">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="79ad6-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-interchange-envelope"></a><span data-ttu-id="79ad6-109">配置交换信封</span><span class="sxs-lookup"><span data-stu-id="79ad6-109">To configure the interchange envelope</span></span>  
  
1.  <span data-ttu-id="79ad6-110">创建 EDIFACT 编码协议中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。</span><span class="sxs-lookup"><span data-stu-id="79ad6-110">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="79ad6-111">若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="79ad6-111">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="79ad6-112">单向协议选项卡上，在**交换设置**部分中，单击**包络线**。</span><span class="sxs-lookup"><span data-stu-id="79ad6-112">On a one-way agreement tab, under **Interchange Settings** section, click **Envelopes**.</span></span>  
  
3.  <span data-ttu-id="79ad6-113">有关**处理优先级代码 (UNB8)**，输入最少包含一个字符，最多一个字符的字母值。</span><span class="sxs-lookup"><span data-stu-id="79ad6-113">For **Processing priority code (UNB8)**, enter an alphabetical value with a minimum of one character and a maximum of one character.</span></span> <span data-ttu-id="79ad6-114">此字段为可选字段。</span><span class="sxs-lookup"><span data-stu-id="79ad6-114">This is an optional field.</span></span>  
  
4.  <span data-ttu-id="79ad6-115">有关**通信协议 (UNB10)**，输入一个字母数字值，该值最少包含一个字符，最多 35 个字符。</span><span class="sxs-lookup"><span data-stu-id="79ad6-115">For **Communication agreement (UNB10)**, enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="79ad6-116">此字段为可选字段</span><span class="sxs-lookup"><span data-stu-id="79ad6-116">This is an optional field</span></span>  
  
5.  <span data-ttu-id="79ad6-117">选择**测试指示器 (UNB11)** 以指示该交换生成的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是测试数据。</span><span class="sxs-lookup"><span data-stu-id="79ad6-117">Select **Test indicator (UNB11)** to indicate that the interchange generated by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is test data.</span></span>  
  
6.  <span data-ttu-id="79ad6-118">选择**应用 UNA 段 （字符串服务建议）** 生成 UNA 段为要发送的交换。</span><span class="sxs-lookup"><span data-stu-id="79ad6-118">Select **Apply UNA segment (String service advice)** to generate a UNA segment for the interchange to be sent.</span></span> <span data-ttu-id="79ad6-119">如果选中此选项，然后**UNA6**不能为空和**UNA 6 后缀**不能为**无**。</span><span class="sxs-lookup"><span data-stu-id="79ad6-119">If this option is checked, then **UNA6** cannot be empty and **UNA 6 Suffix** cannot be **None**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="79ad6-120">你指定**UNA6**和**UNA6 后缀**中**字符集和分隔符**页中所述[配置字符集和分隔符 (EDIFACT)](../core/configuring-charset-and-separators-edifact.md).</span><span class="sxs-lookup"><span data-stu-id="79ad6-120">You specify **UNA6** and **UNA6 Suffix** in the **Charset and Separators** page as described in [Configuring Charset and Separators (EDIFACT)](../core/configuring-charset-and-separators-edifact.md).</span></span>  
  
7.  <span data-ttu-id="79ad6-121">选择**应用 UNG 段 （功能组标头）** 创建分组段的功能组标头中传出消息。</span><span class="sxs-lookup"><span data-stu-id="79ad6-121">Select **Apply UNG segments (Functional group header)** to create grouping segments in the functional group header in outgoing messages.</span></span>  
  
8.  <span data-ttu-id="79ad6-122">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="79ad6-122">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79ad6-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79ad6-123">See Also</span></span>  
 [<span data-ttu-id="79ad6-124">配置交换设置 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="79ad6-124">Configuring Interchange Settings (EDIFACT)</span></span>](../core/configuring-interchange-settings-edifact.md)