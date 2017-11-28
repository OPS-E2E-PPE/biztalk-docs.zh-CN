---
title: "配置常规参与方属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bbabf7e5-6388-4900-ad47-cf5d5af396b5
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a4bb40e943cc06f298db01142590e2a133c1ee05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-general-party-properties"></a><span data-ttu-id="a92c5-102">配置常规参与方属性</span><span class="sxs-lookup"><span data-stu-id="a92c5-102">Configuring General Party Properties</span></span>
<span data-ttu-id="a92c5-103">参与方或贸易合作伙伴表示业务关系中的一个参与组织。</span><span class="sxs-lookup"><span data-stu-id="a92c5-103">A party or trading partner represents a participating organization in a business relationship.</span></span> <span data-ttu-id="a92c5-104">参与方属性包含下列信息：</span><span class="sxs-lookup"><span data-stu-id="a92c5-104">Party properties contain the following information:</span></span>  
  
-   <span data-ttu-id="a92c5-105">常规信息（如参与方名称）</span><span class="sxs-lookup"><span data-stu-id="a92c5-105">General information such as party name</span></span>  
  
-   <span data-ttu-id="a92c5-106">与该参与方关联的发送端口</span><span class="sxs-lookup"><span data-stu-id="a92c5-106">Send ports associated with the party</span></span>  
  
-   <span data-ttu-id="a92c5-107">与该参与方关联的证书</span><span class="sxs-lookup"><span data-stu-id="a92c5-107">Certificates associated with the party</span></span>  
  
 <span data-ttu-id="a92c5-108">有关方或贸易合作伙伴的详细信息，请参阅[贸易合作伙伴](../core/trading-partners-and-business-profiles.md)。</span><span class="sxs-lookup"><span data-stu-id="a92c5-108">For more information about parties or trading partners, see [Trading Partners](../core/trading-partners-and-business-profiles.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a92c5-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="a92c5-109">Prerequisites</span></span>  
 <span data-ttu-id="a92c5-110">必须以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理员组或 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators 组成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="a92c5-110">You must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators or [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] B2B Operators group.</span></span>  
  
### <a name="to-configure-party-properties"></a><span data-ttu-id="a92c5-111">配置参与方属性</span><span class="sxs-lookup"><span data-stu-id="a92c5-111">To configure party properties</span></span>  
  
1.  <span data-ttu-id="a92c5-112">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右键单击**方**，指向**新建**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="a92c5-112">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-click **Parties**, point to **New**, and then click **Party**.</span></span>  
  
2.  <span data-ttu-id="a92c5-113">上**常规**页**参与方属性**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a92c5-113">On the **General** page of the **Party Properties** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="a92c5-114">使用此选项</span><span class="sxs-lookup"><span data-stu-id="a92c5-114">Use this</span></span>|<span data-ttu-id="a92c5-115">执行的操作</span><span class="sxs-lookup"><span data-stu-id="a92c5-115">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a92c5-116">**名称**</span><span class="sxs-lookup"><span data-stu-id="a92c5-116">**Name**</span></span>|<span data-ttu-id="a92c5-117">输入参与方名称。</span><span class="sxs-lookup"><span data-stu-id="a92c5-117">Enter a party name.</span></span>|  
    |<span data-ttu-id="a92c5-118">**本地 BizTalk 处理接收方或支持从该参与方发送消息的消息**</span><span class="sxs-lookup"><span data-stu-id="a92c5-118">**Local BizTalk processes messages received by the party or supports sending messages from this party**</span></span>|<span data-ttu-id="a92c5-119">选中此复选框以指定该参与方代表托管 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的同一个贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="a92c5-119">Select this checkbox to specify that the party represents the same trading partner that also hosts [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="a92c5-120">**重要说明：**两方 Tpm 使用全新的管道的解决方案附带[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，你必须选择至少一个方此复选框。</span><span class="sxs-lookup"><span data-stu-id="a92c5-120">**Important:**  For a two-party TPM solution that uses out-of-the-box pipelines shipped with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], you must select this check box for at least one party.</span></span> <span data-ttu-id="a92c5-121">**注意：**如果清除此复选框，将创建此参与方的协议时禁用某些属性。</span><span class="sxs-lookup"><span data-stu-id="a92c5-121">**Note:**  If you clear this check box, some properties will be disabled while creating the agreements for this party.</span></span>|  
    |<span data-ttu-id="a92c5-122">**其他属性 – 名称/值**</span><span class="sxs-lookup"><span data-stu-id="a92c5-122">**Additional Properties – Name / Value**</span></span>|<span data-ttu-id="a92c5-123">输入一个名称/值对以存储有关参与方的任何信息。</span><span class="sxs-lookup"><span data-stu-id="a92c5-123">Enter a name-value pair to store any information about the party.</span></span> <span data-ttu-id="a92c5-124">可以根据需要添加任意数量的名称/值对。</span><span class="sxs-lookup"><span data-stu-id="a92c5-124">You can add as many name-value pairs as you want.</span></span> <span data-ttu-id="a92c5-125">**注意：**名称-值对不用于 BizTalk server 任何处理; 此数据是仅供信息。</span><span class="sxs-lookup"><span data-stu-id="a92c5-125">**Note:**  The name-value pairs are not used by the BizTalk Server for any processing; this data is for information purposes only.</span></span>|  
    |<span data-ttu-id="a92c5-126">**删除**</span><span class="sxs-lookup"><span data-stu-id="a92c5-126">**Delete**</span></span>|<span data-ttu-id="a92c5-127">单击此项可删除所选的名称/值对。</span><span class="sxs-lookup"><span data-stu-id="a92c5-127">Click to delete the selected name-value pair.</span></span>|  
  
3.  <span data-ttu-id="a92c5-128">上**发送端口**页**参与方属性**对话框框中，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="a92c5-128">On the **Send Ports** page of the **Party Properties** dialog box, do the following.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a92c5-129">在 [!INCLUDE[prague](../includes/prague-md.md)] 中，发送端口关联在协议级别执行。</span><span class="sxs-lookup"><span data-stu-id="a92c5-129">In [!INCLUDE[prague](../includes/prague-md.md)], the send port association is done at the agreement level.</span></span> <span data-ttu-id="a92c5-130">**发送端口**作为一部分的参与方属性是只是为了向后兼容，会出现页面。</span><span class="sxs-lookup"><span data-stu-id="a92c5-130">The **Send Ports** page available as part of the party properties is purely for backward compatibility.</span></span> <span data-ttu-id="a92c5-131">每当您将发送端口与协议相关联时，发送端口设置也会传播到参与方设置，您同时会在此页面上看到发送端口关联。</span><span class="sxs-lookup"><span data-stu-id="a92c5-131">Whenever you associate a send port with an agreement, the send port setting is also propagated to the party setting and you can see the send port association in this page as well.</span></span> <span data-ttu-id="a92c5-132">但是，反之则不然。</span><span class="sxs-lookup"><span data-stu-id="a92c5-132">However, the reverse is not true.</span></span> <span data-ttu-id="a92c5-133">不能将发送端口与参与方关联，然后使该发送端口自动作为协议设置的一部分使用。</span><span class="sxs-lookup"><span data-stu-id="a92c5-133">You cannot associate a send port with a party and then have that send port be automatically available as part of the agreement settings.</span></span> <span data-ttu-id="a92c5-134">有关如何将发送端口与协议关联的详细信息，请参阅[配置发送的端口关联 (X12)](../core/configuring-send-port-association-x12.md)或[配置发送端口关联 (EDIFACT)](../core/configuring-send-port-association-edifact.md)。</span><span class="sxs-lookup"><span data-stu-id="a92c5-134">For more information on how to associate send ports with agreement, see [Configuring Send Port Association (X12)](../core/configuring-send-port-association-x12.md) or [Configuring Send Port Association (EDIFACT)](../core/configuring-send-port-association-edifact.md).</span></span>  
  
    |<span data-ttu-id="a92c5-135">使用此选项</span><span class="sxs-lookup"><span data-stu-id="a92c5-135">Use this</span></span>|<span data-ttu-id="a92c5-136">执行的操作</span><span class="sxs-lookup"><span data-stu-id="a92c5-136">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a92c5-137">**发送端口的名称**</span><span class="sxs-lookup"><span data-stu-id="a92c5-137">**Send ports - Name**</span></span>|<span data-ttu-id="a92c5-138">从下拉列表中选择要绑定到此参与方的发送端口。</span><span class="sxs-lookup"><span data-stu-id="a92c5-138">From the drop-down list, select a send port to bind to this party.</span></span>|  
    |<span data-ttu-id="a92c5-139">**发送端口的 URI**</span><span class="sxs-lookup"><span data-stu-id="a92c5-139">**Send ports - URI**</span></span>|<span data-ttu-id="a92c5-140">显示发送端口地址。</span><span class="sxs-lookup"><span data-stu-id="a92c5-140">Displays the send port address.</span></span>|  
    |<span data-ttu-id="a92c5-141">**删除**</span><span class="sxs-lookup"><span data-stu-id="a92c5-141">**Remove**</span></span>|<span data-ttu-id="a92c5-142">单击此项可删除所选从该参与方发送端口。</span><span class="sxs-lookup"><span data-stu-id="a92c5-142">Click to remove the selected send port from the party.</span></span>|  
    |<span data-ttu-id="a92c5-143">**属性**</span><span class="sxs-lookup"><span data-stu-id="a92c5-143">**Properties**</span></span>|<span data-ttu-id="a92c5-144">单击此项可显示**发送端口属性**所选的发送端口的对话框。</span><span class="sxs-lookup"><span data-stu-id="a92c5-144">Click to display the **Send Port Properties** dialog box for the selected send port.</span></span>|  
  
4.  <span data-ttu-id="a92c5-145">上**证书**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="a92c5-145">On the **Certificate** page, do the following:</span></span>  
  
    |<span data-ttu-id="a92c5-146">使用此选项</span><span class="sxs-lookup"><span data-stu-id="a92c5-146">Use this</span></span>|<span data-ttu-id="a92c5-147">执行的操作</span><span class="sxs-lookup"><span data-stu-id="a92c5-147">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a92c5-148">**浏览**</span><span class="sxs-lookup"><span data-stu-id="a92c5-148">**Browse**</span></span>|<span data-ttu-id="a92c5-149">单击此项可显示**选择证书**对话框中，其中从本地计算机或其他人证书存储，将应用到消息传输到方选择签名证书。</span><span class="sxs-lookup"><span data-stu-id="a92c5-149">Click to display the **Select Certificate** dialog box, where you select the signature certificate from the Local Machine or Other People certificate store to apply to messages transmitted to the party.</span></span>|  
    |<span data-ttu-id="a92c5-150">**公用名**</span><span class="sxs-lookup"><span data-stu-id="a92c5-150">**Common Name**</span></span>|<span data-ttu-id="a92c5-151">显示所选证书的说明。</span><span class="sxs-lookup"><span data-stu-id="a92c5-151">Displays a description of the selected certificate.</span></span>|  
    |<span data-ttu-id="a92c5-152">**指纹**</span><span class="sxs-lookup"><span data-stu-id="a92c5-152">**Thumbprint**</span></span>|<span data-ttu-id="a92c5-153">显示用于参与方解析和签名验证的私钥证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="a92c5-153">Displays the thumbprint of the private key certificate that is used for party resolution and signature verification.</span></span> <span data-ttu-id="a92c5-154">证书指纹的格式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 是十六进制数字 （介于 0 到 9） 或从 A 到 F 字母。</span><span class="sxs-lookup"><span data-stu-id="a92c5-154">The certificate thumbprint has the format HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, where H is a hexadecimal digit (a number from 0 through 9 or a letter from A through F).</span></span>|  
    |<span data-ttu-id="a92c5-155">**删除证书**</span><span class="sxs-lookup"><span data-stu-id="a92c5-155">**Remove certificate**</span></span>|<span data-ttu-id="a92c5-156">单击此项可删除所显示证书。</span><span class="sxs-lookup"><span data-stu-id="a92c5-156">Click to remove the displayed certificate.</span></span>|  
  
5.  <span data-ttu-id="a92c5-157">单击**应用**接受属性，或单击**确定**完成的配置设置。</span><span class="sxs-lookup"><span data-stu-id="a92c5-157">Click **Apply** to accept the properties, or click **OK** to complete the configuration setting.</span></span> <span data-ttu-id="a92c5-158">以上任一操作均将验证设置。</span><span class="sxs-lookup"><span data-stu-id="a92c5-158">Either action will validate the settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a92c5-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a92c5-159">See Also</span></span>  
 [<span data-ttu-id="a92c5-160">配置 EDI 属性</span><span class="sxs-lookup"><span data-stu-id="a92c5-160">Configuring EDI Properties</span></span>](../core/configuring-edi-properties.md)