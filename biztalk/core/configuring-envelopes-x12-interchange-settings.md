---
title: "配置信封 （X12 交换设置） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4fade73-14cf-475c-81b5-6102c75db991
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf4f88ee1e5d786367c1a4bc0f5b2404fd5c1a37
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-envelopes-x12-interchange-settings"></a><span data-ttu-id="74b13-102">配置信封（X 12 交换设置）</span><span class="sxs-lookup"><span data-stu-id="74b13-102">Configuring Envelopes (X12-Interchange Settings)</span></span>
<span data-ttu-id="74b13-103">X12 交换信封生成设置定义 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 如何生成要发送到接收方的 X12 编码交换的信封。</span><span class="sxs-lookup"><span data-stu-id="74b13-103">X12 interchange envelope generation settings define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates the envelope of an X12-encoded interchange to be sent to the receiving party.</span></span> <span data-ttu-id="74b13-104">在本部分中，您可以定义 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 如何为它发送到参与方的 X12 编码的交换生成 ISA 段。</span><span class="sxs-lookup"><span data-stu-id="74b13-104">In this section, you define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates the ISA segment for an X12-encoded interchange that it sends to the party.</span></span> <span data-ttu-id="74b13-105">ISA 段是 X12 编码的交换的交换控制标头。</span><span class="sxs-lookup"><span data-stu-id="74b13-105">An ISA segment is the interchange control header for an X12-encoded interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74b13-106">对于 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 运行时，字母数字 ISA 字段的长度是固定的。</span><span class="sxs-lookup"><span data-stu-id="74b13-106">For the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime, the length of alphanumeric ISA fields is fixed.</span></span> <span data-ttu-id="74b13-107">但是，对于[!INCLUDE[TPM](../includes/tpm-md.md)]用户界面，您可以为字母数字的 ISA 字段输入单个字符。</span><span class="sxs-lookup"><span data-stu-id="74b13-107">However, for the [!INCLUDE[TPM](../includes/tpm-md.md)] user interface, you may enter a single character for an alphanumeric ISA field.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="74b13-108">将填充尾随空格字符，以确保符合标准要求使用这些字段。</span><span class="sxs-lookup"><span data-stu-id="74b13-108"> will pad these fields with trailing space characters to ensure compliance with standards requirements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="74b13-109">此处介绍的设置还适用于 HIPAA 交换信封生成。</span><span class="sxs-lookup"><span data-stu-id="74b13-109">The settings described here also apply to HIPAA interchange envelope generation.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="74b13-110">如果你清除了所有属性会被都禁用此页上**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="74b13-110">All the properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="74b13-111">仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="74b13-111">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="74b13-112">例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="74b13-112">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="74b13-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="74b13-113">Prerequisites</span></span>  
 <span data-ttu-id="74b13-114">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="74b13-114">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-envelope"></a><span data-ttu-id="74b13-115">定义信封</span><span class="sxs-lookup"><span data-stu-id="74b13-115">To define the envelope</span></span>  
  
1.  <span data-ttu-id="74b13-116">创建 X12 编码协议中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="74b13-116">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="74b13-117">若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="74b13-117">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="74b13-118">单向协议选项卡上，在**交换设置**部分中，单击**包络线**。</span><span class="sxs-lookup"><span data-stu-id="74b13-118">On a one-way agreement tab, under **Interchange Settings** section, click **Envelopes**.</span></span>  
  
3.  <span data-ttu-id="74b13-119">下**ISA11 用法**，保留**标准标识符**选择用来指定标准标识符而不是重复分隔符，，然后从下拉列表中选择标准标识符的值。</span><span class="sxs-lookup"><span data-stu-id="74b13-119">Under **ISA11 usage**, keep **Standard identifier** selected to specify a standard identifier instead of a repetition separator, and then select a value for the standard identifier from the drop-down list.</span></span> <span data-ttu-id="74b13-120">选择**重复分隔符**若要指定重复分隔符而不是一个标准的标识符，然后的重复分隔符输入单个字符。</span><span class="sxs-lookup"><span data-stu-id="74b13-120">Select **Repetition separator** to specify a repetition separator instead of a standard identifier, and then enter a single character for the repetition separator.</span></span> <span data-ttu-id="74b13-121">用于分隔在事务集内重复的段的重复分隔符仅限于 ASCII 字符集中的值。</span><span class="sxs-lookup"><span data-stu-id="74b13-121">The repetition separator, which is used to separate segments that repeat within a transaction set, is limited to the values in the ASCII character set.</span></span>  
  
4.  <span data-ttu-id="74b13-122">有关**控制版本号 (ISA12)**，选择的 x12 标准要使用的版本[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用于生成传出交换。</span><span class="sxs-lookup"><span data-stu-id="74b13-122">For **Control version number (ISA12)**, select the version of the X12 standard to be used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for generating an outgoing interchange.</span></span>  
  
5.  <span data-ttu-id="74b13-123">有关**用法指示符 (ISA15)**，选择以指示是否由生成将交换[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是信息、 生产数据还是测试数据。</span><span class="sxs-lookup"><span data-stu-id="74b13-123">For **Usage indicator (ISA15)**, select to indicate whether an interchange generated by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is information, production data, or test data.</span></span>  
  
6.  <span data-ttu-id="74b13-124">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="74b13-124">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74b13-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74b13-125">See Also</span></span>  
 [<span data-ttu-id="74b13-126">配置交换设置 (X12)</span><span class="sxs-lookup"><span data-stu-id="74b13-126">Configuring Interchange Settings (X12)</span></span>](../core/configuring-interchange-settings-x12.md)