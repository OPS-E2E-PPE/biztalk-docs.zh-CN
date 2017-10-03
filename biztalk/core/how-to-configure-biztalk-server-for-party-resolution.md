---
title: "如何将 BizTalk Server 配置为参与方解析 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8ac330b9-3498-4c98-a6e8-d2c02cd641dd
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f9d7a21b4edf5df4bd903763bcb3d1a8a8c6e1ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-biztalk-server-for-party-resolution"></a><span data-ttu-id="170bf-102">如何将 BizTalk Server 配置为参与方解析</span><span class="sxs-lookup"><span data-stu-id="170bf-102">How to Configure BizTalk Server for Party Resolution</span></span>
<span data-ttu-id="170bf-103">下面的过程列出了配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 以便用于参与方解析时需执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="170bf-103">The following procedure lists the steps that you have to follow to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for party resolution.</span></span>  
  
-   <span data-ttu-id="170bf-104">在证书存储中安装证书以接收签名消息</span><span class="sxs-lookup"><span data-stu-id="170bf-104">To install the certificates in the certificates store to receive signed messages</span></span>  
  
-   <span data-ttu-id="170bf-105">创建代表您合作伙伴的参与方</span><span class="sxs-lookup"><span data-stu-id="170bf-105">To create a party to represent your partner</span></span>  
  
-   <span data-ttu-id="170bf-106">创建使用证书进行参与方解析的管道</span><span class="sxs-lookup"><span data-stu-id="170bf-106">To create a pipeline for party resolution using certificates</span></span>  
  
-   <span data-ttu-id="170bf-107">配置使用证书进行参与方解析的接收位置</span><span class="sxs-lookup"><span data-stu-id="170bf-107">To configure the receive location for party resolution using certificates</span></span>  
  
### <a name="to-install-the-certificates-in-the-certificates-store-to-receive-signed-messages"></a><span data-ttu-id="170bf-108">在证书存储中安装证书以接收签名消息</span><span class="sxs-lookup"><span data-stu-id="170bf-108">To install the certificates in the certificates store to receive signed messages</span></span>  
  
1.  <span data-ttu-id="170bf-109">合作伙伴 A 从证书颁发机构 (CA) 请求数字签名的私钥/公钥对。</span><span class="sxs-lookup"><span data-stu-id="170bf-109">Partner A requests a private-public key pair for digital signatures from the certification authority (CA).</span></span>  
  
2.  <span data-ttu-id="170bf-110">合作伙伴 A 向您发送它的数字签名的公钥。</span><span class="sxs-lookup"><span data-stu-id="170bf-110">Partner A sends you its public key for digital signatures.</span></span>  
  
3.  <span data-ttu-id="170bf-111">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，登录到具有特定主机实例（该主机实例运行将从合作伙伴 A 接收消息的处理程序）的服务器上。在“其他人”存储中安装合作伙伴 A 的公钥证书以验证其签名。</span><span class="sxs-lookup"><span data-stu-id="170bf-111">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], log on to the server that has a host instance running a handler that will receive messages from Partner A. Install the Partner A public key certificate to verify their signature in the Other People store.</span></span> <span data-ttu-id="170bf-112">下图显示您安装证书的证书存储。</span><span class="sxs-lookup"><span data-stu-id="170bf-112">The following figure shows the certificate store where you install the certificate.</span></span>  
  
     <span data-ttu-id="170bf-113">![若要接收安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span><span class="sxs-lookup"><span data-stu-id="170bf-113">![Certificates required to receive secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span></span>  
  
4.  <span data-ttu-id="170bf-114">在合作伙伴 A 中，在适当的存储中安装合作伙伴 A 私钥证书以便对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="170bf-114">In Partner A, install the Partner A private key certificate for signing messages in the appropriate store.</span></span> <span data-ttu-id="170bf-115">（如果合作伙伴 A 使用 [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)] 或 [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，则在将对发送到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的消息进行签名的帐户的个人存储中安装私钥。）</span><span class="sxs-lookup"><span data-stu-id="170bf-115">(If Partner A is using [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], or [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], install the private key in the personal store for the account that will sign messages sent to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="170bf-116">与"以接收签名的消息的证书存储中安装证书"的步骤完全相同，则此步骤中[如何安装进行数字签名的证书](../core/how-to-install-the-certificates-for-digital-signatures.md)。</span><span class="sxs-lookup"><span data-stu-id="170bf-116">This step is exactly same as the step "To install the certificates in the certificates store to receive signed messages" in [How to install the Certificates for Digital Signatures](../core/how-to-install-the-certificates-for-digital-signatures.md).</span></span>  
  
### <a name="to-create-a-party-to-represent-your-partner"></a><span data-ttu-id="170bf-117">创建代表您合作伙伴的参与方</span><span class="sxs-lookup"><span data-stu-id="170bf-117">To create a party to represent your partner</span></span>  
  
1.  <span data-ttu-id="170bf-118">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，创建合作伙伴 A.一个参与方有关如何创建参与方的详细信息，请参阅[如何创建参与方](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044)。</span><span class="sxs-lookup"><span data-stu-id="170bf-118">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, create a party for the Partner A. For more information about how to create a Party, see [How to Create a Party](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044).</span></span>  
  
2.  <span data-ttu-id="170bf-119">在**证书**属性中，选择签名证书来用于标识此方，合作伙伴 A.签名的公钥</span><span class="sxs-lookup"><span data-stu-id="170bf-119">In the **Certificates** properties, select the public key signing certificate to use to identify this party, Partner A.</span></span>  
  
### <a name="to-create-a-pipeline-for-party-resolution-using-certificates"></a><span data-ttu-id="170bf-120">创建使用证书进行参与方解析的管道</span><span class="sxs-lookup"><span data-stu-id="170bf-120">To create a pipeline for party resolution using certificates</span></span>  
  
1.  <span data-ttu-id="170bf-121">在 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的解决方案资源管理器中，选择要在其中创建管道的项目。</span><span class="sxs-lookup"><span data-stu-id="170bf-121">In Solution Explorer in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], select the project in which you want to create the pipeline.</span></span>  
  
    1.  <span data-ttu-id="170bf-122">上**文件**菜单上，单击**添加新项**。</span><span class="sxs-lookup"><span data-stu-id="170bf-122">On the **File** menu, click **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="170bf-123">在**添加新项**对话框框中，展开 BizTalk 项目项，单击**管道文件**，然后单击**接收管道**模板。</span><span class="sxs-lookup"><span data-stu-id="170bf-123">In the **Add New Item** dialog box, expand BizTalk Project Items, click **Pipeline Files**, and then click the **Receive Pipeline** template.</span></span>  
  
    3.  <span data-ttu-id="170bf-124">在**名称**字段中，键入管道的名称。</span><span class="sxs-lookup"><span data-stu-id="170bf-124">In the **Name** field, type a name for the pipeline.</span></span>  
  
    4.  <span data-ttu-id="170bf-125">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="170bf-125">Click **Add**.</span></span>  
  
         <span data-ttu-id="170bf-126">此时，新的管道将显示在解决方案资源管理器中。</span><span class="sxs-lookup"><span data-stu-id="170bf-126">The new pipeline appears in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="170bf-127">拖动到 MIME/SMIME 解码器管道组件**解码**接收管道的阶段。</span><span class="sxs-lookup"><span data-stu-id="170bf-127">Drag the MIME/SMIME Decoder pipeline component into the **Decode** stage of a receive pipeline.</span></span>  
  
     <span data-ttu-id="170bf-128">![MIME &#47;SMIME 解码器管道组件](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")</span><span class="sxs-lookup"><span data-stu-id="170bf-128">![MIME&#47;SMIME Decoder pipeline component](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")</span></span>  
  
    -   <span data-ttu-id="170bf-129">配置中的 MIME/SMIME 解码器管道组件属性**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="170bf-129">Configure the MIME/SMIME Decoder pipeline component properties in the **Properties** window.</span></span> <span data-ttu-id="170bf-130">MIME/SMIME 解码器有关的详细信息，请参阅[如何配置 MIME SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="170bf-130">For more information about the MIME/SMIME decoder, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="170bf-131">您可以在将管道部署到某一 BizTalk 组中后，使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置接收位置的管道属性。</span><span class="sxs-lookup"><span data-stu-id="170bf-131">You can configure pipeline properties for a receive location after the pipeline has been deployed into a BizTalk group using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="170bf-132">还可以为 BizTalk 组中的每个接收位置配置不同的管道属性。</span><span class="sxs-lookup"><span data-stu-id="170bf-132">You can configure different pipeline properties for each receive location in the BizTalk group.</span></span> <span data-ttu-id="170bf-133">有关详细信息，请参阅[如何配置为接收位置的每个实例管道属性](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="170bf-133">For more information, see [How to Configure Per-instance Pipeline Properties for a Receive Location](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="170bf-134">MIME/SMIME 解码器管道组件既执行解密，又执行数字签名验证（在配置为执行这两个功能时）。</span><span class="sxs-lookup"><span data-stu-id="170bf-134">The MIME/SMIME Decoder pipeline component performs both decryption and digital signature validation (when configured to perform both functions).</span></span> <span data-ttu-id="170bf-135">因此，如果将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置为接收加密和签名消息，则可以使用同一接收管道。</span><span class="sxs-lookup"><span data-stu-id="170bf-135">Therefore, if you are configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive encrypted and signed messages, you can use the same receive pipeline.</span></span> <span data-ttu-id="170bf-136">换言之，您不必为解密和数字签名验证创建不同的管道。</span><span class="sxs-lookup"><span data-stu-id="170bf-136">In other words, you do not have to create separate pipelines for decryption and digital signature validation.</span></span>  
  
3.  <span data-ttu-id="170bf-137">将参与方解析管道组件到**ResolveParty**接收管道的阶段。</span><span class="sxs-lookup"><span data-stu-id="170bf-137">Drag the Party Resolution pipeline component into the **ResolveParty** stage of a receive pipeline.</span></span> <span data-ttu-id="170bf-138">有关参与方解析管道组件的详细信息，请参阅[如何配置方解析管道组件](../core/how-to-configure-the-party-resolution-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="170bf-138">For more information about the Party Resolution pipeline component, see [How to Configure the Party Resolution Pipeline Component](../core/how-to-configure-the-party-resolution-pipeline-component.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="170bf-139">您还可以使用默认的 XMLReceive 管道，而不用创建新的接收管道。</span><span class="sxs-lookup"><span data-stu-id="170bf-139">You can also use the default XMLReceive pipeline instead of creating a new receive pipeline.</span></span> <span data-ttu-id="170bf-140">XMLReceive 管道运行参与方解析组件，解析将证书使用者方 id。</span><span class="sxs-lookup"><span data-stu-id="170bf-140">The XMLReceive pipeline runs the Party Resolution component, which resolves the certificate subject to the party ID.</span></span> <span data-ttu-id="170bf-141">请注意，XMLReceive 管道具有空的解码阶段，因此不能使用它接收加密的消息或验证数字签名。</span><span class="sxs-lookup"><span data-stu-id="170bf-141">Note that the XMLReceive pipeline has an empty Decode stage, and therefore you cannot use it for receiving encrypted messages or verifying digital signatures.</span></span>  
  
    -   <span data-ttu-id="170bf-142">在属性窗口中，将配置参与方解析管道属性**证书解析参与方**到`True`。</span><span class="sxs-lookup"><span data-stu-id="170bf-142">In the Properties window, configure the Party Resolution pipeline property **Resolve party by certificate** to `True`.</span></span>  
  
4.  <span data-ttu-id="170bf-143">生成并部署接收管道。</span><span class="sxs-lookup"><span data-stu-id="170bf-143">Build and deploy the receive pipeline.</span></span>  
  
### <a name="to-configure-the-receive-location-for-party-resolution-using-certificates"></a><span data-ttu-id="170bf-144">配置使用证书进行参与方解析的接收位置</span><span class="sxs-lookup"><span data-stu-id="170bf-144">To configure the receive location for party resolution using certificates</span></span>  
  
1.  <span data-ttu-id="170bf-145">将您在前面过程中创建的 BizTalk 程序集添加到包括接收位置的 BizTalk 应用程序，以便接收签名消息。</span><span class="sxs-lookup"><span data-stu-id="170bf-145">Add the BizTalk assembly that you created in previous procedure to the BizTalk Application including the receive locations to receive signed messages.</span></span> <span data-ttu-id="170bf-146">有关如何添加 BizTalk 程序集的详细信息，请参阅[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="170bf-146">For more information about how to add BizTalk assemblies, see [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
2.  <span data-ttu-id="170bf-147">使用您在前面过程中创建的接收管道配置 BizTalk 应用程序中的接收位置。</span><span class="sxs-lookup"><span data-stu-id="170bf-147">Configure the receive locations in the BizTalk Application with the receive pipeline that you created in previous procedure.</span></span> <span data-ttu-id="170bf-148">有关如何配置的详细信息接收位置，请参阅[如何编辑接收位置的属性](../core/how-to-edit-the-properties-of-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="170bf-148">For more information about how to configure receive locations, see [How to Edit the Properties of a Receive Location](../core/how-to-edit-the-properties-of-a-receive-location.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="170bf-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="170bf-149">See Also</span></span>  
 <span data-ttu-id="170bf-150">[如何将 BizTalk Server 配置为接收注册消息](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="170bf-150">[How to Configure BizTalk Server for Receiving Signed Messages](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md) </span></span>  
 <span data-ttu-id="170bf-151">[BizTalk Server 用于签名的消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="170bf-151">[Certificates that BizTalk Server Uses for Signed Messages](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span></span>  
 <span data-ttu-id="170bf-152">[入站的消息身份验证](../core/inbound-message-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="170bf-152">[Inbound Message Authentication](../core/inbound-message-authentication.md) </span></span>  
 [<span data-ttu-id="170bf-153">将证书用于参与方解析</span><span class="sxs-lookup"><span data-stu-id="170bf-153">Using Certificates for Party Resolution</span></span>](../core/using-certificates-for-party-resolution.md)