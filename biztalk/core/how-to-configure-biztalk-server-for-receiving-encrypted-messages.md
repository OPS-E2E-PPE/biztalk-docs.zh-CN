---
title: "如何将 BizTalk Server 配置为接收加密的消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bd1e7e4c-f80c-468e-aa86-7c18406feead
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33a4a3ed307f86ec1edba6ef59eee5b806caf75e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-biztalk-server-for-receiving-encrypted-messages"></a><span data-ttu-id="40359-102">如何配置 BizTalk Server 以便接收加密消息</span><span class="sxs-lookup"><span data-stu-id="40359-102">How to Configure BizTalk Server for Receiving Encrypted Messages</span></span>
<span data-ttu-id="40359-103">下面的过程列出了配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 以便接收加密消息需执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="40359-103">The following procedure lists the steps that you have to follow to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive encrypted messages.</span></span>  
  
-   <span data-ttu-id="40359-104">创建管道以便接收加密消息</span><span class="sxs-lookup"><span data-stu-id="40359-104">To create a pipeline to receive encrypted messages</span></span>  
  
-   <span data-ttu-id="40359-105">配置接收位置以便接收加密消息</span><span class="sxs-lookup"><span data-stu-id="40359-105">To configure the receive location for receiving encrypted messages</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="40359-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="40359-106">Prerequisites</span></span>  
 <span data-ttu-id="40359-107">在配置之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s 针对接收加密的消息，你必须执行中的步骤[如何安装证书的加密消息](../core/how-to-install-the-certificates-for-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="40359-107">Before configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s for receiving encrypted messages, you must perform the steps in [How to Install the Certificates for Encrypted Messages](../core/how-to-install-the-certificates-for-encrypted-messages.md).</span></span>  
  
### <a name="to-create-a-pipeline-to-receive-encrypted-messages"></a><span data-ttu-id="40359-108">创建管道以便接收加密消息</span><span class="sxs-lookup"><span data-stu-id="40359-108">To create a pipeline to receive encrypted messages</span></span>  
  
1.  <span data-ttu-id="40359-109">在 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的解决方案资源管理器中，选择要在其中创建管道的项目。</span><span class="sxs-lookup"><span data-stu-id="40359-109">In Solution Explorer in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], select the project in which you want to create the pipeline.</span></span>  
  
    1.  <span data-ttu-id="40359-110">上**文件**菜单上，单击**添加新项**。</span><span class="sxs-lookup"><span data-stu-id="40359-110">On the **File** menu, click **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="40359-111">在**添加新项**对话框框中，展开 BizTalk 项目项，单击**管道文件**，然后单击**接收管道**模板。</span><span class="sxs-lookup"><span data-stu-id="40359-111">In the **Add New Item** dialog box, expand BizTalk Project Items, click **Pipeline Files**, and then click the **Receive Pipeline** template.</span></span>  
  
    3.  <span data-ttu-id="40359-112">在**名称**字段中，键入管道的名称。</span><span class="sxs-lookup"><span data-stu-id="40359-112">In the **Name** field, type a name for the pipeline.</span></span>  
  
    4.  <span data-ttu-id="40359-113">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="40359-113">Click **Add**.</span></span>  
  
         <span data-ttu-id="40359-114">此时，新的管道将显示在解决方案资源管理器中。</span><span class="sxs-lookup"><span data-stu-id="40359-114">The new pipeline appears in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="40359-115">将 MIME/SMIME 解码器管道组件拖至接收管道的“解码”阶段。</span><span class="sxs-lookup"><span data-stu-id="40359-115">Drag the MIME/SMIME Decoder pipeline component into the Decode stage of a receive pipeline.</span></span>  
  
     <span data-ttu-id="40359-116">![MIME &#47;SMIME 解码器管道组件](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")</span><span class="sxs-lookup"><span data-stu-id="40359-116">![MIME&#47;SMIME Decoder pipeline component](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")</span></span>  
  
    -   <span data-ttu-id="40359-117">配置中的 MIME/SMIME 解码器管道组件属性**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="40359-117">Configure the MIME/SMIME Decoder pipeline component properties in the **Properties** window.</span></span> <span data-ttu-id="40359-118">MIME/SMIME 解码器有关的详细信息，请参阅[如何配置 MIME SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="40359-118">For more information about the MIME/SMIME decoder, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="40359-119">您可以在将管道部署到某一 BizTalk 组中后，使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置接收位置的管道属性。</span><span class="sxs-lookup"><span data-stu-id="40359-119">You can configure pipeline properties for a receive location after the pipeline has been deployed into a BizTalk group using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="40359-120">还可以为 BizTalk 组中的每个接收位置配置不同的管道属性。</span><span class="sxs-lookup"><span data-stu-id="40359-120">You can configure different pipeline properties for each receive location in the BizTalk group.</span></span> <span data-ttu-id="40359-121">有关详细信息，请参阅[如何配置为接收位置的每个实例管道属性](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="40359-121">For more information, see [How to Configure Per-instance Pipeline Properties for a Receive Location](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="40359-122">MIME/SMIME 解码器管道组件既执行解密，又执行数字签名验证（在配置为执行这两个功能时）。</span><span class="sxs-lookup"><span data-stu-id="40359-122">The MIME/SMIME Decoder pipeline component performs both decryption and digital signature validation (when configured to perform both functions).</span></span> <span data-ttu-id="40359-123">因此，如果将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置为接收加密和签名消息，则可以使用同一接收管道。</span><span class="sxs-lookup"><span data-stu-id="40359-123">Therefore, if you are configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive encrypted and signed messages, you can use the same receive pipeline.</span></span> <span data-ttu-id="40359-124">换言之，您不必为解密和数字签名验证创建不同的管道。</span><span class="sxs-lookup"><span data-stu-id="40359-124">In other words, you do not have to create separate pipelines for decryption and digital signature validation.</span></span>  
  
3.  <span data-ttu-id="40359-125">生成并部署接收管道。</span><span class="sxs-lookup"><span data-stu-id="40359-125">Build and deploy the receive pipeline.</span></span>  
  
### <a name="to-configure-the-receive-location-for-receiving-encrypted-messages"></a><span data-ttu-id="40359-126">配置接收位置以便接收加密消息</span><span class="sxs-lookup"><span data-stu-id="40359-126">To configure the receive location for receiving encrypted messages</span></span>  
  
1.  <span data-ttu-id="40359-127">将您在前面过程中创建的 BizTalk 程序集添加到包括接收位置的 BizTalk 应用程序，以便接收加密消息。</span><span class="sxs-lookup"><span data-stu-id="40359-127">Add the BizTalk assembly that you created in previous procedure to the BizTalk Application including the receive locations to receive encrypted messages.</span></span> <span data-ttu-id="40359-128">有关如何添加 BizTalk 程序集的详细信息，请参阅[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="40359-128">For more information about how to add BizTalk assemblies, see [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
2.  <span data-ttu-id="40359-129">使用您在前面过程中创建的接收管道配置 BizTalk 应用程序中的接收位置。</span><span class="sxs-lookup"><span data-stu-id="40359-129">Configure the receive locations in the BizTalk Application with the receive pipeline that you created in previous procedure.</span></span> <span data-ttu-id="40359-130">有关如何配置的详细信息接收位置，请参阅[如何编辑接收位置的属性](../core/how-to-edit-the-properties-of-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="40359-130">For more information about how to configure receive locations, see [How to Edit the Properties of a Receive Location](../core/how-to-edit-the-properties-of-a-receive-location.md).</span></span>  
  
3.  <span data-ttu-id="40359-131">配置主机用作接收处理程序接收位置与在过程中，安装的解密证书"以接收加密的消息配置 BizTalk 主机"中[如何安装证书的加密消息](../core/how-to-install-the-certificates-for-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="40359-131">Configure the host used as receive handler for the receive location with the decryption certificate that you installed in the procedure," To configure BizTalk hosts for receiving encrypted messages" in [How to Install the Certificates for Encrypted Messages](../core/how-to-install-the-certificates-for-encrypted-messages.md).</span></span> <span data-ttu-id="40359-132">有关详细信息如何配置主机属性，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="40359-132">For more information how to configure host properties, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40359-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="40359-133">See Also</span></span>  
 <span data-ttu-id="40359-134">[BizTalk Server 用于加密消息的证书](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span><span class="sxs-lookup"><span data-stu-id="40359-134">[Certificates that BizTalk Server Uses for Encrypted Messages](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span></span>  
 <span data-ttu-id="40359-135">[如何将 BizTalk Server 配置为发送加密的消息](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md) </span><span class="sxs-lookup"><span data-stu-id="40359-135">[How to Configure BizTalk Server for Sending Encrypted Messages](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md) </span></span>  
 [<span data-ttu-id="40359-136">发送和接收加密的消息</span><span class="sxs-lookup"><span data-stu-id="40359-136">Sending and Receiving Encrypted Messages</span></span>](../core/sending-and-receiving-encrypted-messages.md)