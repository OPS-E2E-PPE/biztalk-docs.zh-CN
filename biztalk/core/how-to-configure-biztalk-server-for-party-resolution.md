---
title: 如何为参与方解析配置 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ac330b9-3498-4c98-a6e8-d2c02cd641dd
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8d6fc4f0f0dc61b111060aebb26b8dccfc32ec15
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36991054"
---
# <a name="how-to-configure-biztalk-server-for-party-resolution"></a><span data-ttu-id="ad44a-102">如何为参与方解析配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="ad44a-102">How to Configure BizTalk Server for Party Resolution</span></span>
<span data-ttu-id="ad44a-103">下面的过程列出了配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 以便用于参与方解析时需执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="ad44a-103">The following procedure lists the steps that you have to follow to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for party resolution.</span></span>  
  
-   <span data-ttu-id="ad44a-104">在证书存储中安装证书以接收签名消息</span><span class="sxs-lookup"><span data-stu-id="ad44a-104">To install the certificates in the certificates store to receive signed messages</span></span>  
  
-   <span data-ttu-id="ad44a-105">创建代表您合作伙伴的参与方</span><span class="sxs-lookup"><span data-stu-id="ad44a-105">To create a party to represent your partner</span></span>  
  
-   <span data-ttu-id="ad44a-106">创建使用证书进行参与方解析的管道</span><span class="sxs-lookup"><span data-stu-id="ad44a-106">To create a pipeline for party resolution using certificates</span></span>  
  
-   <span data-ttu-id="ad44a-107">配置使用证书进行参与方解析的接收位置</span><span class="sxs-lookup"><span data-stu-id="ad44a-107">To configure the receive location for party resolution using certificates</span></span>  
  
### <a name="to-install-the-certificates-in-the-certificates-store-to-receive-signed-messages"></a><span data-ttu-id="ad44a-108">在证书存储中安装证书以接收签名消息</span><span class="sxs-lookup"><span data-stu-id="ad44a-108">To install the certificates in the certificates store to receive signed messages</span></span>  
  
1. <span data-ttu-id="ad44a-109">合作伙伴 A 从证书颁发机构 (CA) 请求数字签名的私钥/公钥对。</span><span class="sxs-lookup"><span data-stu-id="ad44a-109">Partner A requests a private-public key pair for digital signatures from the certification authority (CA).</span></span>  
  
2. <span data-ttu-id="ad44a-110">合作伙伴 A 向您发送它的数字签名的公钥。</span><span class="sxs-lookup"><span data-stu-id="ad44a-110">Partner A sends you its public key for digital signatures.</span></span>  
  
3. <span data-ttu-id="ad44a-111">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，登录到具有特定主机实例（该主机实例运行将从合作伙伴 A 接收消息的处理程序）的服务器上。在“其他人”存储中安装合作伙伴 A 的公钥证书以验证其签名。</span><span class="sxs-lookup"><span data-stu-id="ad44a-111">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], log on to the server that has a host instance running a handler that will receive messages from Partner A. Install the Partner A public key certificate to verify their signature in the Other People store.</span></span> <span data-ttu-id="ad44a-112">下图显示您安装证书的证书存储。</span><span class="sxs-lookup"><span data-stu-id="ad44a-112">The following figure shows the certificate store where you install the certificate.</span></span>  
  
    <span data-ttu-id="ad44a-113">![若要接收安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span><span class="sxs-lookup"><span data-stu-id="ad44a-113">![Certificates required to receive secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span></span>  
  
4. <span data-ttu-id="ad44a-114">在合作伙伴 A 中，在适当的存储中安装合作伙伴 A 私钥证书以便对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="ad44a-114">In Partner A, install the Partner A private key certificate for signing messages in the appropriate store.</span></span> <span data-ttu-id="ad44a-115">（如果合作伙伴 A 使用 [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)] 或 [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，则在将对发送到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的消息进行签名的帐户的个人存储中安装私钥。）</span><span class="sxs-lookup"><span data-stu-id="ad44a-115">(If Partner A is using [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], or [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], install the private key in the personal store for the account that will sign messages sent to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].)</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ad44a-116">与"以接收签名的消息的证书存储中安装证书"步骤完全相同，则此步骤中[如何安装证书进行数字签名](../core/how-to-install-the-certificates-for-digital-signatures.md)。</span><span class="sxs-lookup"><span data-stu-id="ad44a-116">This step is exactly same as the step "To install the certificates in the certificates store to receive signed messages" in [How to install the Certificates for Digital Signatures](../core/how-to-install-the-certificates-for-digital-signatures.md).</span></span>  
  
### <a name="to-create-a-party-to-represent-your-partner"></a><span data-ttu-id="ad44a-117">创建代表您合作伙伴的参与方</span><span class="sxs-lookup"><span data-stu-id="ad44a-117">To create a party to represent your partner</span></span>  
  
1. <span data-ttu-id="ad44a-118">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，创建代表合作伙伴 a。有关如何创建一个参与方的详细信息，请参阅[如何创建参与方](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044)。</span><span class="sxs-lookup"><span data-stu-id="ad44a-118">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, create a party for the Partner A. For more information about how to create a Party, see [How to Create a Party](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044).</span></span>  
  
2. <span data-ttu-id="ad44a-119">在中**证书**属性中，选择公钥签名证书，用于标识此参与方合作伙伴 a。</span><span class="sxs-lookup"><span data-stu-id="ad44a-119">In the **Certificates** properties, select the public key signing certificate to use to identify this party, Partner A.</span></span>  
  
### <a name="to-create-a-pipeline-for-party-resolution-using-certificates"></a><span data-ttu-id="ad44a-120">创建使用证书进行参与方解析的管道</span><span class="sxs-lookup"><span data-stu-id="ad44a-120">To create a pipeline for party resolution using certificates</span></span>  
  
1. <span data-ttu-id="ad44a-121">在 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的解决方案资源管理器中，选择要在其中创建管道的项目。</span><span class="sxs-lookup"><span data-stu-id="ad44a-121">In Solution Explorer in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], select the project in which you want to create the pipeline.</span></span>  
  
   1.  <span data-ttu-id="ad44a-122">上**文件**菜单上，单击**添加新项**。</span><span class="sxs-lookup"><span data-stu-id="ad44a-122">On the **File** menu, click **Add New Item**.</span></span>  
  
   2.  <span data-ttu-id="ad44a-123">在中**添加新项**对话框框中，展开 BizTalk 项目项，单击**管道文件**，然后单击**接收管道**模板。</span><span class="sxs-lookup"><span data-stu-id="ad44a-123">In the **Add New Item** dialog box, expand BizTalk Project Items, click **Pipeline Files**, and then click the **Receive Pipeline** template.</span></span>  
  
   3.  <span data-ttu-id="ad44a-124">在中**名称**字段中，键入管道的名称。</span><span class="sxs-lookup"><span data-stu-id="ad44a-124">In the **Name** field, type a name for the pipeline.</span></span>  
  
   4.  <span data-ttu-id="ad44a-125">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="ad44a-125">Click **Add**.</span></span>  
  
        <span data-ttu-id="ad44a-126">此时，新的管道将显示在解决方案资源管理器中。</span><span class="sxs-lookup"><span data-stu-id="ad44a-126">The new pipeline appears in Solution Explorer.</span></span>  
  
2. <span data-ttu-id="ad44a-127">将到 MIME/SMIME 解码器管道组件拖放**解码**接收管道阶段。</span><span class="sxs-lookup"><span data-stu-id="ad44a-127">Drag the MIME/SMIME Decoder pipeline component into the **Decode** stage of a receive pipeline.</span></span>  
  
    <span data-ttu-id="ad44a-128">![MIME&#47;SMIME 解码器管道组件](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")</span><span class="sxs-lookup"><span data-stu-id="ad44a-128">![MIME&#47;SMIME Decoder pipeline component](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")</span></span>  
  
   -   <span data-ttu-id="ad44a-129">配置 MIME/SMIME 解码器管道组件属性中的**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="ad44a-129">Configure the MIME/SMIME Decoder pipeline component properties in the **Properties** window.</span></span> <span data-ttu-id="ad44a-130">有关 MIME/SMIME 解码器的详细信息，请参阅[如何配置 MIME-SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="ad44a-130">For more information about the MIME/SMIME decoder, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ad44a-131">您可以在将管道部署到某一 BizTalk 组中后，使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置接收位置的管道属性。</span><span class="sxs-lookup"><span data-stu-id="ad44a-131">You can configure pipeline properties for a receive location after the pipeline has been deployed into a BizTalk group using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="ad44a-132">还可以为 BizTalk 组中的每个接收位置配置不同的管道属性。</span><span class="sxs-lookup"><span data-stu-id="ad44a-132">You can configure different pipeline properties for each receive location in the BizTalk group.</span></span> <span data-ttu-id="ad44a-133">有关详细信息，请参阅[如何配置每个实例的接收位置的管道属性](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="ad44a-133">For more information, see [How to Configure Per-instance Pipeline Properties for a Receive Location](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md).</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="ad44a-134">MIME/SMIME 解码器管道组件既执行解密，又执行数字签名验证（在配置为执行这两个功能时）。</span><span class="sxs-lookup"><span data-stu-id="ad44a-134">The MIME/SMIME Decoder pipeline component performs both decryption and digital signature validation (when configured to perform both functions).</span></span> <span data-ttu-id="ad44a-135">因此，如果将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置为接收加密和签名消息，则可以使用同一接收管道。</span><span class="sxs-lookup"><span data-stu-id="ad44a-135">Therefore, if you are configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive encrypted and signed messages, you can use the same receive pipeline.</span></span> <span data-ttu-id="ad44a-136">换言之，您不必为解密和数字签名验证创建不同的管道。</span><span class="sxs-lookup"><span data-stu-id="ad44a-136">In other words, you do not have to create separate pipelines for decryption and digital signature validation.</span></span>  
  
3. <span data-ttu-id="ad44a-137">将到参与方解析管道组件拖放**解析参与方**接收管道阶段。</span><span class="sxs-lookup"><span data-stu-id="ad44a-137">Drag the Party Resolution pipeline component into the **ResolveParty** stage of a receive pipeline.</span></span> <span data-ttu-id="ad44a-138">有关参与方解析管道组件的详细信息，请参阅[如何配置参与方解析管道组件](../core/how-to-configure-the-party-resolution-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="ad44a-138">For more information about the Party Resolution pipeline component, see [How to Configure the Party Resolution Pipeline Component](../core/how-to-configure-the-party-resolution-pipeline-component.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="ad44a-139">您还可以使用默认的 XMLReceive 管道，而不用创建新的接收管道。</span><span class="sxs-lookup"><span data-stu-id="ad44a-139">You can also use the default XMLReceive pipeline instead of creating a new receive pipeline.</span></span> <span data-ttu-id="ad44a-140">XMLReceive 管道运行参与方解析组件，解析将证书使用者参与方 id。</span><span class="sxs-lookup"><span data-stu-id="ad44a-140">The XMLReceive pipeline runs the Party Resolution component, which resolves the certificate subject to the party ID.</span></span> <span data-ttu-id="ad44a-141">请注意，XMLReceive 管道具有空的解码阶段，因此不能接收加密的消息或验证数字签名使用它。</span><span class="sxs-lookup"><span data-stu-id="ad44a-141">Note that the XMLReceive pipeline has an empty Decode stage, and therefore you cannot use it for receiving encrypted messages or verifying digital signatures.</span></span>  
  
   -   <span data-ttu-id="ad44a-142">在属性窗口中，将配置参与方解析管道属性**证书解析参与方**到`True`。</span><span class="sxs-lookup"><span data-stu-id="ad44a-142">In the Properties window, configure the Party Resolution pipeline property **Resolve party by certificate** to `True`.</span></span>  
  
4. <span data-ttu-id="ad44a-143">生成并部署接收管道。</span><span class="sxs-lookup"><span data-stu-id="ad44a-143">Build and deploy the receive pipeline.</span></span>  
  
### <a name="to-configure-the-receive-location-for-party-resolution-using-certificates"></a><span data-ttu-id="ad44a-144">配置使用证书进行参与方解析的接收位置</span><span class="sxs-lookup"><span data-stu-id="ad44a-144">To configure the receive location for party resolution using certificates</span></span>  
  
1.  <span data-ttu-id="ad44a-145">将您在前面过程中创建的 BizTalk 程序集添加到包括接收位置的 BizTalk 应用程序，以便接收签名消息。</span><span class="sxs-lookup"><span data-stu-id="ad44a-145">Add the BizTalk assembly that you created in previous procedure to the BizTalk Application including the receive locations to receive signed messages.</span></span> <span data-ttu-id="ad44a-146">有关如何添加 BizTalk 程序集的详细信息，请参阅[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="ad44a-146">For more information about how to add BizTalk assemblies, see [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
2.  <span data-ttu-id="ad44a-147">使用您在前面过程中创建的接收管道配置 BizTalk 应用程序中的接收位置。</span><span class="sxs-lookup"><span data-stu-id="ad44a-147">Configure the receive locations in the BizTalk Application with the receive pipeline that you created in previous procedure.</span></span> <span data-ttu-id="ad44a-148">详细了解如何配置接收位置，请参阅[如何编辑接收位置属性](../core/how-to-edit-the-properties-of-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="ad44a-148">For more information about how to configure receive locations, see [How to Edit the Properties of a Receive Location](../core/how-to-edit-the-properties-of-a-receive-location.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad44a-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad44a-149">See Also</span></span>  
 <span data-ttu-id="ad44a-150">[如何配置 BizTalk Server 以便接收签名消息](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="ad44a-150">[How to Configure BizTalk Server for Receiving Signed Messages](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md) </span></span>  
 <span data-ttu-id="ad44a-151">[BizTalk Server 用于签名消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="ad44a-151">[Certificates that BizTalk Server Uses for Signed Messages](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span></span>  
 <span data-ttu-id="ad44a-152">[入站的消息身份验证](../core/inbound-message-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="ad44a-152">[Inbound Message Authentication](../core/inbound-message-authentication.md) </span></span>  
 [<span data-ttu-id="ad44a-153">为参与方解析使用证书</span><span class="sxs-lookup"><span data-stu-id="ad44a-153">Using Certificates for Party Resolution</span></span>](../core/using-certificates-for-party-resolution.md)