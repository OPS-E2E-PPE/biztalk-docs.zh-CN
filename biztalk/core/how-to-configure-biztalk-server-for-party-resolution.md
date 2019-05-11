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
ms.openlocfilehash: 6186b4b9d6f027738eacf79034afc739cb5f4619
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341559"
---
# <a name="how-to-configure-biztalk-server-for-party-resolution"></a><span data-ttu-id="4fb99-102">如何为参与方解析配置 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="4fb99-102">How to Configure BizTalk Server for Party Resolution</span></span>
<span data-ttu-id="4fb99-103">以下过程列出了您必须按照配置的步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]进行参与方解析。</span><span class="sxs-lookup"><span data-stu-id="4fb99-103">The following procedure lists the steps that you have to follow to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] for party resolution.</span></span>  
  
-   <span data-ttu-id="4fb99-104">若要以接收签名的消息的证书存储中安装证书</span><span class="sxs-lookup"><span data-stu-id="4fb99-104">To install the certificates in the certificates store to receive signed messages</span></span>  
  
-   <span data-ttu-id="4fb99-105">若要创建代表您合作伙伴的参与方</span><span class="sxs-lookup"><span data-stu-id="4fb99-105">To create a party to represent your partner</span></span>  
  
-   <span data-ttu-id="4fb99-106">若要创建使用证书的参与方解析管道</span><span class="sxs-lookup"><span data-stu-id="4fb99-106">To create a pipeline for party resolution using certificates</span></span>  
  
-   <span data-ttu-id="4fb99-107">若要配置使用证书的参与方解析的接收位置</span><span class="sxs-lookup"><span data-stu-id="4fb99-107">To configure the receive location for party resolution using certificates</span></span>  
  
### <a name="to-install-the-certificates-in-the-certificates-store-to-receive-signed-messages"></a><span data-ttu-id="4fb99-108">若要以接收签名的消息的证书存储中安装证书</span><span class="sxs-lookup"><span data-stu-id="4fb99-108">To install the certificates in the certificates store to receive signed messages</span></span>  
  
1. <span data-ttu-id="4fb99-109">合作伙伴 A 从证书颁发机构 (CA) 请求数字签名的私钥 / 公钥对。</span><span class="sxs-lookup"><span data-stu-id="4fb99-109">Partner A requests a private-public key pair for digital signatures from the certification authority (CA).</span></span>  
  
2. <span data-ttu-id="4fb99-110">合作伙伴 A 向您发送其公钥数字签名。</span><span class="sxs-lookup"><span data-stu-id="4fb99-110">Partner A sends you its public key for digital signatures.</span></span>  
  
3. <span data-ttu-id="4fb99-111">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，登录到服务器的已存储的主机实例运行将从合作伙伴 A.安装接收消息的处理程序的合作伙伴的公钥证书以验证其他人在其签名。</span><span class="sxs-lookup"><span data-stu-id="4fb99-111">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], log on to the server that has a host instance running a handler that will receive messages from Partner A. Install the Partner A public key certificate to verify their signature in the Other People store.</span></span> <span data-ttu-id="4fb99-112">下图显示了你在其中安装证书的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="4fb99-112">The following figure shows the certificate store where you install the certificate.</span></span>  
  
    <span data-ttu-id="4fb99-113">![若要接收安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span><span class="sxs-lookup"><span data-stu-id="4fb99-113">![Certificates required to receive secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span></span>  
  
4. <span data-ttu-id="4fb99-114">在合作伙伴 A 中，安装合作伙伴 A 私钥证书在适当的存储中的消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="4fb99-114">In Partner A, install the Partner A private key certificate for signing messages in the appropriate store.</span></span> <span data-ttu-id="4fb99-115">(如果合作伙伴 A 使用[!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]，或[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]，或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，将发送到的消息进行签名的帐户的个人存储中安装私钥[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。)</span><span class="sxs-lookup"><span data-stu-id="4fb99-115">(If Partner A is using [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], or [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], install the private key in the personal store for the account that will sign messages sent to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].)</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4fb99-116">与"以接收签名的消息的证书存储中安装证书"步骤完全相同，则此步骤中[如何安装证书进行数字签名](../core/how-to-install-the-certificates-for-digital-signatures.md)。</span><span class="sxs-lookup"><span data-stu-id="4fb99-116">This step is exactly same as the step "To install the certificates in the certificates store to receive signed messages" in [How to install the Certificates for Digital Signatures](../core/how-to-install-the-certificates-for-digital-signatures.md).</span></span>  
  
### <a name="to-create-a-party-to-represent-your-partner"></a><span data-ttu-id="4fb99-117">若要创建代表您合作伙伴的参与方</span><span class="sxs-lookup"><span data-stu-id="4fb99-117">To create a party to represent your partner</span></span>  
  
1. <span data-ttu-id="4fb99-118">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，创建代表合作伙伴 a。有关如何创建一个参与方的详细信息，请参阅[如何创建参与方](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044)。</span><span class="sxs-lookup"><span data-stu-id="4fb99-118">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, create a party for the Partner A. For more information about how to create a Party, see [How to Create a Party](http://msdn.microsoft.com/library/f6feca1d-bc83-4fb6-981d-26c9e0d53044).</span></span>  
  
2. <span data-ttu-id="4fb99-119">在中**证书**属性中，选择公钥签名证书，用于标识此参与方合作伙伴 a。</span><span class="sxs-lookup"><span data-stu-id="4fb99-119">In the **Certificates** properties, select the public key signing certificate to use to identify this party, Partner A.</span></span>  
  
### <a name="to-create-a-pipeline-for-party-resolution-using-certificates"></a><span data-ttu-id="4fb99-120">若要创建使用证书的参与方解析管道</span><span class="sxs-lookup"><span data-stu-id="4fb99-120">To create a pipeline for party resolution using certificates</span></span>  
  
1. <span data-ttu-id="4fb99-121">在解决方案资源管理器在 microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，选择想要创建管道的项目。</span><span class="sxs-lookup"><span data-stu-id="4fb99-121">In Solution Explorer in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], select the project in which you want to create the pipeline.</span></span>  
  
   1.  <span data-ttu-id="4fb99-122">上**文件**菜单上，单击**添加新项**。</span><span class="sxs-lookup"><span data-stu-id="4fb99-122">On the **File** menu, click **Add New Item**.</span></span>  
  
   2.  <span data-ttu-id="4fb99-123">在中**添加新项**对话框框中，展开 BizTalk 项目项，单击**管道文件**，然后单击**接收管道**模板。</span><span class="sxs-lookup"><span data-stu-id="4fb99-123">In the **Add New Item** dialog box, expand BizTalk Project Items, click **Pipeline Files**, and then click the **Receive Pipeline** template.</span></span>  
  
   3.  <span data-ttu-id="4fb99-124">在中**名称**字段中，键入管道的名称。</span><span class="sxs-lookup"><span data-stu-id="4fb99-124">In the **Name** field, type a name for the pipeline.</span></span>  
  
   4.  <span data-ttu-id="4fb99-125">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="4fb99-125">Click **Add**.</span></span>  
  
        <span data-ttu-id="4fb99-126">在解决方案资源管理器中将显示新的管道。</span><span class="sxs-lookup"><span data-stu-id="4fb99-126">The new pipeline appears in Solution Explorer.</span></span>  
  
2. <span data-ttu-id="4fb99-127">将到 MIME/SMIME 解码器管道组件拖放**解码**接收管道阶段。</span><span class="sxs-lookup"><span data-stu-id="4fb99-127">Drag the MIME/SMIME Decoder pipeline component into the **Decode** stage of a receive pipeline.</span></span>  
  
    <span data-ttu-id="4fb99-128">![MIME&#47;SMIME 解码器管道组件](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")</span><span class="sxs-lookup"><span data-stu-id="4fb99-128">![MIME&#47;SMIME Decoder pipeline component](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")</span></span>  
  
   -   <span data-ttu-id="4fb99-129">配置 MIME/SMIME 解码器管道组件属性中的**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="4fb99-129">Configure the MIME/SMIME Decoder pipeline component properties in the **Properties** window.</span></span> <span data-ttu-id="4fb99-130">有关 MIME/SMIME 解码器的详细信息，请参阅[如何配置 MIME-SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="4fb99-130">For more information about the MIME/SMIME decoder, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4fb99-131">管道部署到 BizTalk 组使用后，可以配置接收位置的管道属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="4fb99-131">You can configure pipeline properties for a receive location after the pipeline has been deployed into a BizTalk group using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="4fb99-132">每个接收位置在 BizTalk 组中，可以配置不同的管道属性。</span><span class="sxs-lookup"><span data-stu-id="4fb99-132">You can configure different pipeline properties for each receive location in the BizTalk group.</span></span> <span data-ttu-id="4fb99-133">有关详细信息，请参阅[如何配置每个实例的接收位置的管道属性](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="4fb99-133">For more information, see [How to Configure Per-instance Pipeline Properties for a Receive Location](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md).</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="4fb99-134">MIME/SMIME 解码器管道组件执行解密和数字签名验证 （如果配置为执行这两个函数）。</span><span class="sxs-lookup"><span data-stu-id="4fb99-134">The MIME/SMIME Decoder pipeline component performs both decryption and digital signature validation (when configured to perform both functions).</span></span> <span data-ttu-id="4fb99-135">因此，如果你要配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收加密和签名消息，则可以使用相同的接收管道。</span><span class="sxs-lookup"><span data-stu-id="4fb99-135">Therefore, if you are configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive encrypted and signed messages, you can use the same receive pipeline.</span></span> <span data-ttu-id="4fb99-136">换而言之，不需要创建单独的管道解密和数字签名验证。</span><span class="sxs-lookup"><span data-stu-id="4fb99-136">In other words, you do not have to create separate pipelines for decryption and digital signature validation.</span></span>  
  
3. <span data-ttu-id="4fb99-137">将到参与方解析管道组件拖放**解析参与方**接收管道阶段。</span><span class="sxs-lookup"><span data-stu-id="4fb99-137">Drag the Party Resolution pipeline component into the **ResolveParty** stage of a receive pipeline.</span></span> <span data-ttu-id="4fb99-138">有关参与方解析管道组件的详细信息，请参阅[如何配置参与方解析管道组件](../core/how-to-configure-the-party-resolution-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="4fb99-138">For more information about the Party Resolution pipeline component, see [How to Configure the Party Resolution Pipeline Component](../core/how-to-configure-the-party-resolution-pipeline-component.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="4fb99-139">此外可以使用默认的 XMLReceive 管道而不是创建新的接收管道。</span><span class="sxs-lookup"><span data-stu-id="4fb99-139">You can also use the default XMLReceive pipeline instead of creating a new receive pipeline.</span></span> <span data-ttu-id="4fb99-140">XMLReceive 管道运行参与方解析组件，解析将证书使用者参与方 id。</span><span class="sxs-lookup"><span data-stu-id="4fb99-140">The XMLReceive pipeline runs the Party Resolution component, which resolves the certificate subject to the party ID.</span></span> <span data-ttu-id="4fb99-141">请注意，XMLReceive 管道具有空的解码阶段，因此不能接收加密的消息或验证数字签名使用它。</span><span class="sxs-lookup"><span data-stu-id="4fb99-141">Note that the XMLReceive pipeline has an empty Decode stage, and therefore you cannot use it for receiving encrypted messages or verifying digital signatures.</span></span>  
  
   -   <span data-ttu-id="4fb99-142">在属性窗口中，将配置参与方解析管道属性**证书解析参与方**到`True`。</span><span class="sxs-lookup"><span data-stu-id="4fb99-142">In the Properties window, configure the Party Resolution pipeline property **Resolve party by certificate** to `True`.</span></span>  
  
4. <span data-ttu-id="4fb99-143">生成并部署接收管道。</span><span class="sxs-lookup"><span data-stu-id="4fb99-143">Build and deploy the receive pipeline.</span></span>  
  
### <a name="to-configure-the-receive-location-for-party-resolution-using-certificates"></a><span data-ttu-id="4fb99-144">若要配置使用证书的参与方解析的接收位置</span><span class="sxs-lookup"><span data-stu-id="4fb99-144">To configure the receive location for party resolution using certificates</span></span>  
  
1.  <span data-ttu-id="4fb99-145">BizTalk 将添加到包括接收位置接收到 BizTalk 应用程序的上一个过程中创建程序集签名消息。</span><span class="sxs-lookup"><span data-stu-id="4fb99-145">Add the BizTalk assembly that you created in previous procedure to the BizTalk Application including the receive locations to receive signed messages.</span></span> <span data-ttu-id="4fb99-146">有关如何添加 BizTalk 程序集的详细信息，请参阅[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="4fb99-146">For more information about how to add BizTalk assemblies, see [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
2.  <span data-ttu-id="4fb99-147">在上一过程中创建的接收管道在 BizTalk 应用程序中配置的接收位置。</span><span class="sxs-lookup"><span data-stu-id="4fb99-147">Configure the receive locations in the BizTalk Application with the receive pipeline that you created in previous procedure.</span></span> <span data-ttu-id="4fb99-148">详细了解如何配置接收位置，请参阅[如何编辑接收位置属性](../core/how-to-edit-the-properties-of-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="4fb99-148">For more information about how to configure receive locations, see [How to Edit the Properties of a Receive Location](../core/how-to-edit-the-properties-of-a-receive-location.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fb99-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="4fb99-149">See Also</span></span>  
 <span data-ttu-id="4fb99-150">[如何配置 BizTalk Server 以便接收签名消息](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="4fb99-150">[How to Configure BizTalk Server for Receiving Signed Messages](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md) </span></span>  
 <span data-ttu-id="4fb99-151">[BizTalk Server 用于签名消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="4fb99-151">[Certificates that BizTalk Server Uses for Signed Messages](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span></span>  
 <span data-ttu-id="4fb99-152">[入站的消息身份验证](../core/inbound-message-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="4fb99-152">[Inbound Message Authentication](../core/inbound-message-authentication.md) </span></span>  
 [<span data-ttu-id="4fb99-153">为参与方解析使用证书</span><span class="sxs-lookup"><span data-stu-id="4fb99-153">Using Certificates for Party Resolution</span></span>](../core/using-certificates-for-party-resolution.md)