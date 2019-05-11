---
title: 配置信封 （X12-交换设置） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4fade73-14cf-475c-81b5-6102c75db991
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7b2371943f1c422addf5ac31682f92cf36bd368
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355774"
---
# <a name="configuring-envelopes-x12-interchange-settings"></a><span data-ttu-id="1b0c2-102">配置信封（X 12 交换设置）</span><span class="sxs-lookup"><span data-stu-id="1b0c2-102">Configuring Envelopes (X12-Interchange Settings)</span></span>
<span data-ttu-id="1b0c2-103">X12 交换信封生成设置定义如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成要发送到接收方的 X12 编码交换的信封。</span><span class="sxs-lookup"><span data-stu-id="1b0c2-103">X12 interchange envelope generation settings define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates the envelope of an X12-encoded interchange to be sent to the receiving party.</span></span> <span data-ttu-id="1b0c2-104">在本部分中，可以定义如何[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]生成在它发送到参与方的 X12 编码交换的 ISA 段。</span><span class="sxs-lookup"><span data-stu-id="1b0c2-104">In this section, you define how [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] generates the ISA segment for an X12-encoded interchange that it sends to the party.</span></span> <span data-ttu-id="1b0c2-105">ISA 段是 X12 编码交换的交换控制标头。</span><span class="sxs-lookup"><span data-stu-id="1b0c2-105">An ISA segment is the interchange control header for an X12-encoded interchange.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1b0c2-106">有关[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]字母数字 ISA 字段的长度固定的运行时。</span><span class="sxs-lookup"><span data-stu-id="1b0c2-106">For the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] runtime, the length of alphanumeric ISA fields is fixed.</span></span> <span data-ttu-id="1b0c2-107">但是，对于[!INCLUDE[TPM](../includes/tpm-md.md)]用户界面，则可以为字母数字 ISA 字段输入单个字符。</span><span class="sxs-lookup"><span data-stu-id="1b0c2-107">However, for the [!INCLUDE[TPM](../includes/tpm-md.md)] user interface, you may enter a single character for an alphanumeric ISA field.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="1b0c2-108">将填充这些字段用尾随空格字符，以确保符合标准要求。</span><span class="sxs-lookup"><span data-stu-id="1b0c2-108">will pad these fields with trailing space characters to ensure compliance with standards requirements.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="1b0c2-109">此处所述的设置也适用于 HIPAA 交换信封生成。</span><span class="sxs-lookup"><span data-stu-id="1b0c2-109">The settings described here also apply to HIPAA interchange envelope generation.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="1b0c2-110">如果你清除了所有属性会都禁用此页上**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="1b0c2-110">All the properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
> 
>  <span data-ttu-id="1b0c2-111">仅在与参与方所发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="1b0c2-111">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="1b0c2-112">例如，如果创建两个参与方 Party A 和参与方 B，并且对于参与方 A 清除该复选框，上述列表中的属性上禁用**参与方 A-> 参与方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="1b0c2-112">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1b0c2-113">先决条件</span><span class="sxs-lookup"><span data-stu-id="1b0c2-113">Prerequisites</span></span>  
 <span data-ttu-id="1b0c2-114">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="1b0c2-114">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-define-the-envelope"></a><span data-ttu-id="1b0c2-115">若要定义信封</span><span class="sxs-lookup"><span data-stu-id="1b0c2-115">To define the envelope</span></span>  
  
1. <span data-ttu-id="1b0c2-116">创建 X12 编码协议，如中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="1b0c2-116">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="1b0c2-117">若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="1b0c2-117">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2. <span data-ttu-id="1b0c2-118">在单向协议选项卡下**交换设置**部分中，单击**信封**。</span><span class="sxs-lookup"><span data-stu-id="1b0c2-118">On a one-way agreement tab, under **Interchange Settings** section, click **Envelopes**.</span></span>  
  
3. <span data-ttu-id="1b0c2-119">下**ISA11 用法**，保留**标准标识符**选择指定一个标准标识符而不是重复分隔符，并从下拉列表中选择标准标识符的值。</span><span class="sxs-lookup"><span data-stu-id="1b0c2-119">Under **ISA11 usage**, keep **Standard identifier** selected to specify a standard identifier instead of a repetition separator, and then select a value for the standard identifier from the drop-down list.</span></span> <span data-ttu-id="1b0c2-120">选择**重复分隔符**若要指定重复分隔符而非标准标识符，然后再为此重复分隔符输入单个字符。</span><span class="sxs-lookup"><span data-stu-id="1b0c2-120">Select **Repetition separator** to specify a repetition separator instead of a standard identifier, and then enter a single character for the repetition separator.</span></span> <span data-ttu-id="1b0c2-121">用于分隔事务集内重复的段的重复分隔符仅限于 ASCII 字符集中的值。</span><span class="sxs-lookup"><span data-stu-id="1b0c2-121">The repetition separator, which is used to separate segments that repeat within a transaction set, is limited to the values in the ASCII character set.</span></span>  
  
4. <span data-ttu-id="1b0c2-122">有关**控制版本号 (ISA12)**，选择的 x12 标准，供版本[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用于生成传出交换。</span><span class="sxs-lookup"><span data-stu-id="1b0c2-122">For **Control version number (ISA12)**, select the version of the X12 standard to be used by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for generating an outgoing interchange.</span></span>  
  
5. <span data-ttu-id="1b0c2-123">有关**用法指示符 (ISA15)**，选择以指示生成的交换[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是信息、 生产数据还是测试数据。</span><span class="sxs-lookup"><span data-stu-id="1b0c2-123">For **Usage indicator (ISA15)**, select to indicate whether an interchange generated by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is information, production data, or test data.</span></span>  
  
6. <span data-ttu-id="1b0c2-124">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="1b0c2-124">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b0c2-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b0c2-125">See Also</span></span>  
 [<span data-ttu-id="1b0c2-126">配置交换设置 (X12)</span><span class="sxs-lookup"><span data-stu-id="1b0c2-126">Configuring Interchange Settings (X12)</span></span>](../core/configuring-interchange-settings-x12.md)