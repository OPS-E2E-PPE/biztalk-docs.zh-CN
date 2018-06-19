---
title: 配置发送端口关联 (EDIFACT) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d7faabc7-072c-408c-bbd5-f0a039be81f8
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 629bde13f8edc9074b3e6bcb4741746e3de8e1a6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26005974"
---
# <a name="configuring-send-port-association-edifact"></a><span data-ttu-id="95947-102">配置发送端口关联（EDIFACT）</span><span class="sxs-lookup"><span data-stu-id="95947-102">Configuring Send Port Association (EDIFACT)</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="95947-103"> 使用发送端口关联来解析传出 EDI 交换的协议。</span><span class="sxs-lookup"><span data-stu-id="95947-103"> uses send port association to resolve an agreement for an outgoing EDI interchange.</span></span> <span data-ttu-id="95947-104">通过匹配订阅该消息的发送端口与协议关联的发送端口，将 EDI 交换解析为协议。</span><span class="sxs-lookup"><span data-stu-id="95947-104">An EDI interchange is resolved to an agreement by matching the send port that subscribed to the message with the send port associated with an agreement.</span></span> <span data-ttu-id="95947-105">本主题提供有关如何将发送端口与协议相关联的说明。</span><span class="sxs-lookup"><span data-stu-id="95947-105">This topic provides instructions on how to associate send ports to an agreement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="95947-106">如果同一发送端口与多个协议关联，BizTalk Server 将生成错误。</span><span class="sxs-lookup"><span data-stu-id="95947-106">If the same send port is associated with multiple agreements, BizTalk Server will generate an error.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="95947-107">在 BizTalk Server 中，仅在协议级别完成发送端口关联。</span><span class="sxs-lookup"><span data-stu-id="95947-107">In BizTalk Server, the send port association is done only at the agreement level.</span></span> <span data-ttu-id="95947-108">但是，在 BizTalk Server 2009 中，发送端口与参与方级别关联。</span><span class="sxs-lookup"><span data-stu-id="95947-108">However, in BizTalk Server 2009, the send ports were associated at the party level.</span></span> <span data-ttu-id="95947-109">为了向后兼容，**发送端口**都还可以使用页面的参与方属性一部分 (请参阅[配置常规参与方属性](../core/configuring-general-party-properties.md))。</span><span class="sxs-lookup"><span data-stu-id="95947-109">For backward compatibility, a **Send Ports** page is also available as part of the party properties (see [Configuring General Party Properties](../core/configuring-general-party-properties.md)).</span></span> <span data-ttu-id="95947-110">每当您将发送端口与协议相关联时，发送端口设置也会传播到参与方设置，您同时会在此页面上看到发送端口关联。</span><span class="sxs-lookup"><span data-stu-id="95947-110">Whenever you associate a send port with an agreement, the send port setting is also propagated to the party setting and you can see the send port association in this page as well.</span></span> <span data-ttu-id="95947-111">但是，反之则不然。</span><span class="sxs-lookup"><span data-stu-id="95947-111">However, the reverse is not true.</span></span> <span data-ttu-id="95947-112">不能将发送端口与参与方关联，然后使该发送端口自动作为协议设置的一部分使用。</span><span class="sxs-lookup"><span data-stu-id="95947-112">You cannot associate a send port with a party and then have that send port be automatically available as part of the agreement settings.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="95947-113">发送端口关联网格禁用此页上，如果你清除**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**时正在创建你为其创建参与方的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="95947-113">The send port association grid is disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="95947-114">仅在与参与方所发送交换的属性对应的单向协议选项卡上禁用该网格。</span><span class="sxs-lookup"><span data-stu-id="95947-114">The grid is disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="95947-115">例如，如果创建两个参与方 A 方和方 B，并且对于方 A，清除复选框，则网格禁用上**A 方-> 方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="95947-115">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the grid is disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="95947-116">先决条件</span><span class="sxs-lookup"><span data-stu-id="95947-116">Prerequisites</span></span>  
 <span data-ttu-id="95947-117">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="95947-117">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-associate-send-ports-with-an-agreement"></a><span data-ttu-id="95947-118">将发送端口与协议相关联</span><span class="sxs-lookup"><span data-stu-id="95947-118">To associate send ports with an agreement</span></span>  
  
1.  <span data-ttu-id="95947-119">创建 EDIFACT 编码协议中所述[配置常规设置 (EDIFACT)](../core/configuring-general-settings-edifact.md)。</span><span class="sxs-lookup"><span data-stu-id="95947-119">Create an EDIFACT encoding agreement as described in [Configuring General Settings (EDIFACT)](../core/configuring-general-settings-edifact.md).</span></span> <span data-ttu-id="95947-120">若要更新现有协议，右键单击在协议**方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="95947-120">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="95947-121">单向协议选项卡上，在**交换设置**部分中，单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="95947-121">On a one-way agreement tab, under **Interchange Settings** section, click **Send Ports**.</span></span>  
  
3.  <span data-ttu-id="95947-122">单击下面的空单元格中**名称**列，然后从下拉列表中，选择要将与协议相关联的发送端口。</span><span class="sxs-lookup"><span data-stu-id="95947-122">Click the empty cell under the **Name** column, and from the drop-down list, select the send port to associate with the agreement.</span></span> <span data-ttu-id="95947-123">**URI**列将显示发送端口地址。</span><span class="sxs-lookup"><span data-stu-id="95947-123">The **URI** column displays the send port address.</span></span>  
  
4.  <span data-ttu-id="95947-124">若要删除发送端口关联，请选择发送端口的行，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="95947-124">To remove a send port association, select the row for a send port and click **Remove**.</span></span>  
  
5.  <span data-ttu-id="95947-125">若要查看发送端口属性，请选择发送端口的行，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="95947-125">To see the properties for a send port, select the row for a send port and click **Properties**.</span></span>  
  
6.  <span data-ttu-id="95947-126">单击**应用**接受所做的更改，然后才能继续进行配置，或单击**确定**验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="95947-126">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95947-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="95947-127">See Also</span></span>  
 [<span data-ttu-id="95947-128">配置交换设置 (EDIFACT)</span><span class="sxs-lookup"><span data-stu-id="95947-128">Configuring Interchange Settings (EDIFACT)</span></span>](../core/configuring-interchange-settings-edifact.md)