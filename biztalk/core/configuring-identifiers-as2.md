---
title: "配置标识符 (AS2) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29f12696-8257-4664-8e61-292678e98b6b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1f4c8ddde24c32f93d003f778b9359d70e87170
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="configuring-identifiers-as2"></a><span data-ttu-id="cf54a-102">配置标识符（AS2）</span><span class="sxs-lookup"><span data-stu-id="cf54a-102">Configuring Identifiers (AS2)</span></span>
<span data-ttu-id="cf54a-103">在合作伙伴协议中，您必须指定发送方和接收方。</span><span class="sxs-lookup"><span data-stu-id="cf54a-103">In the partner agreement, you must specify the sender and receiver parties.</span></span> <span data-ttu-id="cf54a-104">这些值还可用于入站或出站消息的协议解析。</span><span class="sxs-lookup"><span data-stu-id="cf54a-104">These values are also used for agreement resolution for the inbound or outbound messages.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cf54a-105">以下属性禁用此页上，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="cf54a-105">The following properties are disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  -   <span data-ttu-id="cf54a-106">**AS2To**下**其他协议冲突解决程序**部分。</span><span class="sxs-lookup"><span data-stu-id="cf54a-106">**AS2To** under **Additional Agreement Resolvers** section.</span></span>  
>   
>  <span data-ttu-id="cf54a-107">仅在与从参与方发送交换的属性相对应的单向协议选项卡上禁用这些属性。</span><span class="sxs-lookup"><span data-stu-id="cf54a-107">The properties are disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="cf54a-108">例如，如果创建两个参与方 A 方和方 B 和 A 的当事方，清除复选框，则上面的属性列表会禁用上**A 方-> 方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="cf54a-108">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the above list of properties are disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cf54a-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="cf54a-109">Prerequisites</span></span>  
 <span data-ttu-id="cf54a-110">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="cf54a-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-the-identifier-properties"></a><span data-ttu-id="cf54a-111">配置标识符属性</span><span class="sxs-lookup"><span data-stu-id="cf54a-111">To configure the identifier properties</span></span>  
  
1.  <span data-ttu-id="cf54a-112">创建 AS2 协议中所述[配置常规设置 (AS2)](../core/configuring-general-settings-as2.md)。</span><span class="sxs-lookup"><span data-stu-id="cf54a-112">Create an AS2 agreement as described in [Configuring General Settings (AS2)](../core/configuring-general-settings-as2.md).</span></span> <span data-ttu-id="cf54a-113">若要更新现有 AS2 协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="cf54a-113">To update an existing AS2 agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="cf54a-114">单向协议选项卡上，单击**标识符**。</span><span class="sxs-lookup"><span data-stu-id="cf54a-114">On a one-way agreement tab, click **Identifiers**.</span></span>  
  
3.  <span data-ttu-id="cf54a-115">在**AS2-从**页上，指定贸易合作伙伴发送 AS2 消息的名称。</span><span class="sxs-lookup"><span data-stu-id="cf54a-115">In the **AS2-From** page, specify the name of the trading partner sending the AS2 message.</span></span>  
  
4.  <span data-ttu-id="cf54a-116">在**AS2-到**页上，指定贸易合作伙伴接收 AS2 消息的名称。</span><span class="sxs-lookup"><span data-stu-id="cf54a-116">In the **AS2-To** page, specify the name of the trading partner receiving the AS2 message.</span></span>  
  
5.  <span data-ttu-id="cf54a-117">下**其他协议冲突解决程序**部分中，为**AS2To**属性，输入合作伙伴接收消息的其他别名。</span><span class="sxs-lookup"><span data-stu-id="cf54a-117">Under the **Additional Agreement Resolvers** section, for the **AS2To** property, enter an additional alias for the partner that receives the message.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="cf54a-118">此属性是可选的。</span><span class="sxs-lookup"><span data-stu-id="cf54a-118">This property is optional.</span></span> <span data-ttu-id="cf54a-119">此属性可用于向后兼容。</span><span class="sxs-lookup"><span data-stu-id="cf54a-119">This property is available for backward compatibility.</span></span> <span data-ttu-id="cf54a-120">当一方定义从 BizTalk Server 2006 R2 或 BizTalk Server 2009 迁移，到 BizTalk Server 中，在以前版本的一方的名称时[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]用作此属性的值。</span><span class="sxs-lookup"><span data-stu-id="cf54a-120">When a party definition is migrated from BizTalk Server 2006 R2 or BizTalk Server 2009 to BizTalk Server, the name of the party in the previous versions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is included as a value for this property.</span></span> <span data-ttu-id="cf54a-121">这可确保，发生协议解析，并可与 BizTalk Server 使用的现有应用程序和合作伙伴定义。</span><span class="sxs-lookup"><span data-stu-id="cf54a-121">This ensures that the agreement resolution happens and the existing applications and partner definitions can be used with BizTalk Server.</span></span>  
  
6.  <span data-ttu-id="cf54a-122">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="cf54a-122">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf54a-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf54a-123">See Also</span></span>  
 [<span data-ttu-id="cf54a-124">配置 AS2 协议属性</span><span class="sxs-lookup"><span data-stu-id="cf54a-124">Configuring AS2 Agreement Properties</span></span>](../core/configuring-as2-agreement-properties.md)