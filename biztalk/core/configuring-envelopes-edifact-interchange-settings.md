---
title: 配置信封 （EDIFACT-交换设置） |Microsoft Docs
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
ms.openlocfilehash: 45f3f37172f67040a9ff95d083379e1237e56064
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355843"
---
# <a name="configuring-envelopes-edifact-interchange-settings"></a><span data-ttu-id="4b2c5-102">配置信封 （EDIFACT-交换设置）</span><span class="sxs-lookup"><span data-stu-id="4b2c5-102">Configuring Envelopes (EDIFACT-Interchange Settings)</span></span>
<span data-ttu-id="4b2c5-103">本部分说明如何配置为传出 EDIFACT 消息信封。</span><span class="sxs-lookup"><span data-stu-id="4b2c5-103">This section provides instructions on how to configure the envelope for outgoing EDIFACT messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4b2c5-104">如果你清除了所有属性会都禁用此页上**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="4b2c5-104">All the properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="4b2c5-105">仅在与参与方所发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="4b2c5-105">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="4b2c5-106">例如，如果创建两个参与方 Party A 和参与方 B，并且对于参与方 A 清除该复选框，上述列表中的属性上禁用**参与方 A-> 参与方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="4b2c5-106">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4b2c5-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="4b2c5-107">Prerequisites</span></span>  
 <span data-ttu-id="4b2c5-108">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="4b2c5-108">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-interchange-envelope"></a><span data-ttu-id="4b2c5-109">若要配置交换信封</span><span class="sxs-lookup"><span data-stu-id="4b2c5-109">To configure the interchange envelope</span></span>  
  
1. <span data-ttu-id="4b2c5-110">创建 EDIFACT 编码协议，如中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。</span><span class="sxs-lookup"><span data-stu-id="4b2c5-110">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="4b2c5-111">若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="4b2c5-111">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2. <span data-ttu-id="4b2c5-112">在单向协议选项卡下**交换设置**部分中，单击**信封**。</span><span class="sxs-lookup"><span data-stu-id="4b2c5-112">On a one-way agreement tab, under **Interchange Settings** section, click **Envelopes**.</span></span>  
  
3. <span data-ttu-id="4b2c5-113">有关**处理优先级代码 (UNB8)**，输入最少一个字符，最多为 1 个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="4b2c5-113">For **Processing priority code (UNB8)**, enter an alphabetical value with a minimum of one character and a maximum of one character.</span></span> <span data-ttu-id="4b2c5-114">这是一个可选字段。</span><span class="sxs-lookup"><span data-stu-id="4b2c5-114">This is an optional field.</span></span>  
  
4. <span data-ttu-id="4b2c5-115">有关**通信协议 (UNB10)**，输入包含最少一个字符，最多为 35 个字符的字母数字值。</span><span class="sxs-lookup"><span data-stu-id="4b2c5-115">For **Communication agreement (UNB10)**, enter an alphanumeric value with a minimum of one character and a maximum of 35 characters.</span></span> <span data-ttu-id="4b2c5-116">这是一个可选字段</span><span class="sxs-lookup"><span data-stu-id="4b2c5-116">This is an optional field</span></span>  
  
5. <span data-ttu-id="4b2c5-117">选择**测试指示器 (UNB11)** 以指示由生成的交换[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]是测试数据。</span><span class="sxs-lookup"><span data-stu-id="4b2c5-117">Select **Test indicator (UNB11)** to indicate that the interchange generated by [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is test data.</span></span>  
  
6. <span data-ttu-id="4b2c5-118">选择**应用 UNA 段 （字符串服务建议）** 生成要发送交换的 UNA 段。</span><span class="sxs-lookup"><span data-stu-id="4b2c5-118">Select **Apply UNA segment (String service advice)** to generate a UNA segment for the interchange to be sent.</span></span> <span data-ttu-id="4b2c5-119">如果选中此选项，然后**UNA6**不能为空并**UNA 6 后缀**不能为**None**。</span><span class="sxs-lookup"><span data-stu-id="4b2c5-119">If this option is checked, then **UNA6** cannot be empty and **UNA 6 Suffix** cannot be **None**.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4b2c5-120">您指定**UNA6**并**UNA6 后缀**中**字符集和分隔符**页中所述[配置字符集和分隔符 (EDIFACT)](../core/configuring-charset-and-separators-edifact.md).</span><span class="sxs-lookup"><span data-stu-id="4b2c5-120">You specify **UNA6** and **UNA6 Suffix** in the **Charset and Separators** page as described in [Configuring Charset and Separators (EDIFACT)](../core/configuring-charset-and-separators-edifact.md).</span></span>  
  
7. <span data-ttu-id="4b2c5-121">选择**应用 UNG 段 （功能组标头）** 在传出消息的功能组标头中创建分组段。</span><span class="sxs-lookup"><span data-stu-id="4b2c5-121">Select **Apply UNG segments (Functional group header)** to create grouping segments in the functional group header in outgoing messages.</span></span>  
  
8. <span data-ttu-id="4b2c5-122">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="4b2c5-122">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b2c5-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b2c5-123">See Also</span></span>  
 [<span data-ttu-id="4b2c5-124">配置交换设置 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="4b2c5-124">Configuring Interchange Settings (EDIFACT)</span></span>](../core/configuring-interchange-settings-edifact.md)