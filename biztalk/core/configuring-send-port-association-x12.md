---
title: "配置发送端口关联 (X12) |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 496beb0a-fabf-416e-bc3c-d8537097b50e
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 346a01cee16c2d6a2888f981b6573fc1a0d135b5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-send-port-association-x12"></a><span data-ttu-id="627ce-102">配置发送端口关联（X12）</span><span class="sxs-lookup"><span data-stu-id="627ce-102">Configuring Send Port Association (X12)</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="627ce-103"> 使用发送端口关联来解析传出 EDI 交换的协议。</span><span class="sxs-lookup"><span data-stu-id="627ce-103"> uses send port association to resolve an agreement for an outgoing EDI interchange.</span></span> <span data-ttu-id="627ce-104">通过匹配订阅该消息的发送端口与协议关联的发送端口，将 EDI 交换解析为协议。</span><span class="sxs-lookup"><span data-stu-id="627ce-104">An EDI interchange is resolved to an agreement by matching the send port that subscribed to the message with the send port associated with an agreement.</span></span> <span data-ttu-id="627ce-105">本主题提供有关如何将发送端口与协议相关联的说明。</span><span class="sxs-lookup"><span data-stu-id="627ce-105">This topic provides instructions on how to associate send ports to an agreement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="627ce-106">如果同一发送端口与多个协议关联，BizTalk Server 将生成错误。</span><span class="sxs-lookup"><span data-stu-id="627ce-106">If the same send port is associated with multiple agreements, BizTalk Server will generate an error.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="627ce-107">在 [!INCLUDE[prague](../includes/prague-md.md)]，该信息端口关联仅在协议级别完成。</span><span class="sxs-lookup"><span data-stu-id="627ce-107">In [!INCLUDE[prague](../includes/prague-md.md)], the send port association is done only at the agreement level.</span></span> <span data-ttu-id="627ce-108">但是，在 BizTalk Server 2009 中，发送端口与参与方级别关联。</span><span class="sxs-lookup"><span data-stu-id="627ce-108">However, in BizTalk Server 2009, the send ports were associated at the party level.</span></span> <span data-ttu-id="627ce-109">为了向后兼容，**发送端口**都还可以使用页面的参与方属性一部分 (请参阅[配置常规参与方属性](../core/configuring-general-party-properties.md))。</span><span class="sxs-lookup"><span data-stu-id="627ce-109">For backward compatibility, a **Send Ports** page is also available as part of the party properties (see [Configuring General Party Properties](../core/configuring-general-party-properties.md)).</span></span> <span data-ttu-id="627ce-110">每当您将发送端口与协议相关联时，发送端口设置也会传播到参与方设置，您同时会在此页面上看到发送端口关联。</span><span class="sxs-lookup"><span data-stu-id="627ce-110">Whenever you associate a send port with an agreement, the send port setting is also propagated to the party setting and you can see the send port association in this page as well.</span></span> <span data-ttu-id="627ce-111">但是，反之则不然。</span><span class="sxs-lookup"><span data-stu-id="627ce-111">However, the reverse is not true.</span></span> <span data-ttu-id="627ce-112">不能将发送端口与参与方关联，然后使该发送端口自动作为协议设置的一部分使用。</span><span class="sxs-lookup"><span data-stu-id="627ce-112">You cannot associate a send port with a party and then have that send port be automatically available as part of the agreement settings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="627ce-113">此处所述的设置同样适用于 HIPAA 交换。</span><span class="sxs-lookup"><span data-stu-id="627ce-113">The settings described here also apply to HIPAA interchanges.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="627ce-114">发送端口关联网格禁用此页上，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="627ce-114">The send port association grid is disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="627ce-115">仅在与参与方所发送交换的属性对应的单向协议选项卡上禁用该网格。</span><span class="sxs-lookup"><span data-stu-id="627ce-115">The grid is disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="627ce-116">例如，如果创建两个参与方 A 方和方 B，并且对于方 A，清除复选框，则网格禁用上**A 方-> 方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="627ce-116">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the grid is disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="627ce-117">先决条件</span><span class="sxs-lookup"><span data-stu-id="627ce-117">Prerequisites</span></span>  
 <span data-ttu-id="627ce-118">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="627ce-118">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-associate-send-ports-with-an-agreement"></a><span data-ttu-id="627ce-119">将发送端口与协议相关联</span><span class="sxs-lookup"><span data-stu-id="627ce-119">To associate send ports with an agreement</span></span>  
  
1.  <span data-ttu-id="627ce-120">创建 X12 编码协议中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="627ce-120">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="627ce-121">若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="627ce-121">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="627ce-122">单向协议选项卡上，在**交换设置**部分中，单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="627ce-122">On a one-way agreement tab, under **Interchange Settings** section, click **Send Ports**.</span></span>  
  
3.  <span data-ttu-id="627ce-123">单击下面的空单元格中**名称**列，然后从下拉列表中，选择要将与协议相关联的发送端口。</span><span class="sxs-lookup"><span data-stu-id="627ce-123">Click the empty cell under the **Name** column, and from the drop-down list, select the send port to associate with the agreement.</span></span> <span data-ttu-id="627ce-124">**URI**列将显示发送端口地址。</span><span class="sxs-lookup"><span data-stu-id="627ce-124">The **URI** column displays the send port address.</span></span>  
  
4.  <span data-ttu-id="627ce-125">若要删除发送端口关联，请选择发送端口的行，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="627ce-125">To remove a send port association, select the row for a send port and click **Remove**.</span></span>  
  
5.  <span data-ttu-id="627ce-126">若要查看发送端口属性，请选择发送端口的行，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="627ce-126">To see the properties for a send port, select the row for a send port and click **Properties**.</span></span>  
  
6.  <span data-ttu-id="627ce-127">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="627ce-127">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="627ce-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="627ce-128">See Also</span></span>  
 [<span data-ttu-id="627ce-129">配置交换设置 (X12)</span><span class="sxs-lookup"><span data-stu-id="627ce-129">Configuring Interchange Settings (X12)</span></span>](../core/configuring-interchange-settings-x12.md)