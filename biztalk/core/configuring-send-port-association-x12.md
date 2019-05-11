---
title: 配置发送端口关联 (X12) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 496beb0a-fabf-416e-bc3c-d8537097b50e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bf950110b1eb375579afbe900916e2162fc4c5a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65355307"
---
# <a name="configuring-send-port-association-x12"></a><span data-ttu-id="c4f10-102">配置发送端口关联（X12）</span><span class="sxs-lookup"><span data-stu-id="c4f10-102">Configuring Send Port Association (X12)</span></span>
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="c4f10-103">使用发送端口关联来解析传出 EDI 交换的协议。</span><span class="sxs-lookup"><span data-stu-id="c4f10-103">uses send port association to resolve an agreement for an outgoing EDI interchange.</span></span> <span data-ttu-id="c4f10-104">EDI 交换解析为协议通过匹配订阅消息的发送端口与协议关联的发送端口。</span><span class="sxs-lookup"><span data-stu-id="c4f10-104">An EDI interchange is resolved to an agreement by matching the send port that subscribed to the message with the send port associated with an agreement.</span></span> <span data-ttu-id="c4f10-105">本主题提供有关如何将相关联的说明将发送端口与协议。</span><span class="sxs-lookup"><span data-stu-id="c4f10-105">This topic provides instructions on how to associate send ports to an agreement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4f10-106">如果同一发送端口与多个协议关联，BizTalk Server 将生成错误。</span><span class="sxs-lookup"><span data-stu-id="c4f10-106">If the same send port is associated with multiple agreements, BizTalk Server will generate an error.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c4f10-107">在 BizTalk Server 发送端口关联仅在协议级别完成。</span><span class="sxs-lookup"><span data-stu-id="c4f10-107">In BizTalk Server, the send port association is done only at the agreement level.</span></span> <span data-ttu-id="c4f10-108">但是，在 BizTalk Server 2009 中，发送端口都关联参与方级别。</span><span class="sxs-lookup"><span data-stu-id="c4f10-108">However, in BizTalk Server 2009, the send ports were associated at the party level.</span></span> <span data-ttu-id="c4f10-109">为了向后兼容**发送端口**页也是可用的参与方属性一部分 (请参阅[配置常规参与方属性](../core/configuring-general-party-properties.md))。</span><span class="sxs-lookup"><span data-stu-id="c4f10-109">For backward compatibility, a **Send Ports** page is also available as part of the party properties (see [Configuring General Party Properties](../core/configuring-general-party-properties.md)).</span></span> <span data-ttu-id="c4f10-110">每当将发送端口与协议相关联，也会发送端口设置传播到参与方设置，您可以看到这个页面中的发送端口关联。</span><span class="sxs-lookup"><span data-stu-id="c4f10-110">Whenever you associate a send port with an agreement, the send port setting is also propagated to the party setting and you can see the send port association in this page as well.</span></span> <span data-ttu-id="c4f10-111">但是，反之不成立。</span><span class="sxs-lookup"><span data-stu-id="c4f10-111">However, the reverse is not true.</span></span> <span data-ttu-id="c4f10-112">不能将发送端口与参与方相关联，然后使自动提供该发送端口作为协议设置的一部分。</span><span class="sxs-lookup"><span data-stu-id="c4f10-112">You cannot associate a send port with a party and then have that send port be automatically available as part of the agreement settings.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c4f10-113">此处所述的设置也适用于 HIPAA 交换。</span><span class="sxs-lookup"><span data-stu-id="c4f10-113">The settings described here also apply to HIPAA interchanges.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c4f10-114">发送端口关联网格禁用此页上，如果您清除**本地 BizTalk 处理参与方或支持来自此参与方发送消息的接收的消息**要为其创建的参与方时的复选框协议。</span><span class="sxs-lookup"><span data-stu-id="c4f10-114">The send port association grid is disabled on this page if you cleared the **Local BizTalk processes messages received by the party or supports sending messages from this party** check box while creating the party for which you are creating the agreement.</span></span>  
>   
>  <span data-ttu-id="c4f10-115">仅在与参与方所发送交换的属性相对应的单向协议选项卡上禁用该网格。</span><span class="sxs-lookup"><span data-stu-id="c4f10-115">The grid is disabled only on the one-way agreement tab that corresponds to the properties for interchanges being sent from the party.</span></span> <span data-ttu-id="c4f10-116">例如，如果您创建两个参与方 Party A 和参与方 B，并且对于参与方 A 清除该复选框，网格时禁用了**参与方 A-> 参与方 B**单向协议选项卡。</span><span class="sxs-lookup"><span data-stu-id="c4f10-116">For example, if you create two parties Party A and Party B and for Party A, you cleared the check box, the grid is disabled on the **Party A->Party B** one-way agreement tab.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c4f10-117">先决条件</span><span class="sxs-lookup"><span data-stu-id="c4f10-117">Prerequisites</span></span>  
 <span data-ttu-id="c4f10-118">必须以成员的身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员或[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]B2B Operators 组。</span><span class="sxs-lookup"><span data-stu-id="c4f10-118">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-associate-send-ports-with-an-agreement"></a><span data-ttu-id="c4f10-119">若要将发送端口与协议相关联</span><span class="sxs-lookup"><span data-stu-id="c4f10-119">To associate send ports with an agreement</span></span>  
  
1.  <span data-ttu-id="c4f10-120">创建 X12 编码协议，如中所述[配置常规设置 (X12)](../core/configuring-general-settings-x12.md)。</span><span class="sxs-lookup"><span data-stu-id="c4f10-120">Create an X12 encoding agreement as described in [Configuring General Settings (X12)](../core/configuring-general-settings-x12.md).</span></span> <span data-ttu-id="c4f10-121">若要更新现有的协议，请右键单击中的协议**参与方和业务配置文件**页，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="c4f10-121">To update an existing agreement, right-click the agreement in the **Parties and Business Profiles** page, and click **Properties**.</span></span>  
  
2.  <span data-ttu-id="c4f10-122">在单向协议选项卡下**交换设置**部分中，单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="c4f10-122">On a one-way agreement tab, under **Interchange Settings** section, click **Send Ports**.</span></span>  
  
3.  <span data-ttu-id="c4f10-123">单击下的空单元格**名称**列，然后从下拉列表中，选择要将与协议相关联的发送端口。</span><span class="sxs-lookup"><span data-stu-id="c4f10-123">Click the empty cell under the **Name** column, and from the drop-down list, select the send port to associate with the agreement.</span></span> <span data-ttu-id="c4f10-124">**URI**列将显示发送端口地址。</span><span class="sxs-lookup"><span data-stu-id="c4f10-124">The **URI** column displays the send port address.</span></span>  
  
4.  <span data-ttu-id="c4f10-125">若要删除发送端口关联，请选择发送端口的行，然后单击**删除**。</span><span class="sxs-lookup"><span data-stu-id="c4f10-125">To remove a send port association, select the row for a send port and click **Remove**.</span></span>  
  
5.  <span data-ttu-id="c4f10-126">若要查看为发送端口属性，请选择发送端口的行，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="c4f10-126">To see the properties for a send port, select the row for a send port and click **Properties**.</span></span>  
  
6.  <span data-ttu-id="c4f10-127">单击**Apply**以接受更改，然后才能继续进行配置，或单击**确定**以验证所做的更改，然后关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="c4f10-127">Click **Apply** to accept the changes before continuing with the configuration, or click **OK** to validate the changes and then close the dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4f10-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4f10-128">See Also</span></span>  
 [<span data-ttu-id="c4f10-129">配置交换设置 (X12)</span><span class="sxs-lookup"><span data-stu-id="c4f10-129">Configuring Interchange Settings (X12)</span></span>](../core/configuring-interchange-settings-x12.md)