---
title: 如何配置 BizTalk Server 以便接收签名消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 48479532-24a9-41d9-a3b8-2a23f4e76457
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c05459fbf88882537ea83c6d7697d5707beb6b19
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341563"
---
# <a name="how-to-configure-biztalk-server-for-receiving-signed-messages"></a><span data-ttu-id="2725d-102">如何配置 BizTalk Server 以便接收签名消息</span><span class="sxs-lookup"><span data-stu-id="2725d-102">How to Configure BizTalk Server for Receiving Signed Messages</span></span>
<span data-ttu-id="2725d-103">以下过程列出了您必须按照配置的步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以便接收加密的消息。</span><span class="sxs-lookup"><span data-stu-id="2725d-103">The following procedure lists the steps that you have to follow to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive encrypted messages.</span></span>  
  
-   <span data-ttu-id="2725d-104">若要创建一个管道以接收签名消息</span><span class="sxs-lookup"><span data-stu-id="2725d-104">To create a pipeline to receive signed messages</span></span>  
  
-   <span data-ttu-id="2725d-105">若要配置接收位置以便接收签名消息</span><span class="sxs-lookup"><span data-stu-id="2725d-105">To configure the receive location for receiving signed messages</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2725d-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="2725d-106">Prerequisites</span></span>  
 <span data-ttu-id="2725d-107">配置之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以便接收签名的消息，必须首先执行中的步骤[如何安装证书进行数字签名](../core/how-to-install-the-certificates-for-digital-signatures.md)。</span><span class="sxs-lookup"><span data-stu-id="2725d-107">Before configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s for receiving signed messages, you must perform the steps in [How to install the Certificates for Digital Signatures](../core/how-to-install-the-certificates-for-digital-signatures.md).</span></span>  
  
### <a name="to-create-a-pipeline-to-receive-signed-messages"></a><span data-ttu-id="2725d-108">若要创建一个管道以接收签名消息</span><span class="sxs-lookup"><span data-stu-id="2725d-108">To create a pipeline to receive signed messages</span></span>  
  
1. <span data-ttu-id="2725d-109">在解决方案资源管理器在 microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，选择想要创建管道的项目。</span><span class="sxs-lookup"><span data-stu-id="2725d-109">In Solution Explorer in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], select the project in which you want to create the pipeline.</span></span>  
  
   1.  <span data-ttu-id="2725d-110">上**文件**菜单上，单击**添加新项**。</span><span class="sxs-lookup"><span data-stu-id="2725d-110">On the **File** menu, click **Add New Item**.</span></span>  
  
   2.  <span data-ttu-id="2725d-111">在中**添加新项**对话框框中，展开 BizTalk 项目项，单击**管道文件**，然后单击**接收管道**模板。</span><span class="sxs-lookup"><span data-stu-id="2725d-111">In the **Add New Item** dialog box, expand BizTalk Project Items, click **Pipeline Files**, and then click the **Receive Pipeline** template.</span></span>  
  
   3.  <span data-ttu-id="2725d-112">在中**名称**字段中，键入管道的名称。</span><span class="sxs-lookup"><span data-stu-id="2725d-112">In the **Name** field, type a name for the pipeline.</span></span>  
  
   4.  <span data-ttu-id="2725d-113">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="2725d-113">Click **Add**.</span></span>  
  
        <span data-ttu-id="2725d-114">在解决方案资源管理器中将显示新的管道。</span><span class="sxs-lookup"><span data-stu-id="2725d-114">The new pipeline appears in Solution Explorer.</span></span>  
  
2. <span data-ttu-id="2725d-115">将到 MIME/SMIME 解码器管道组件拖放**解码**接收管道阶段。</span><span class="sxs-lookup"><span data-stu-id="2725d-115">Drag the MIME/SMIME Decoder pipeline component into the **Decode** stage of a receive pipeline.</span></span>  
  
    <span data-ttu-id="2725d-116">![MIME&#47;SMIME 解码器管道组件](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")</span><span class="sxs-lookup"><span data-stu-id="2725d-116">![MIME&#47;SMIME Decoder pipeline component](../core/media/bts-dev-mimesmimedecoder.gif "BTS_DEV_MIMESMIMEDecoder")</span></span>  
  
   -   <span data-ttu-id="2725d-117">配置 MIME/SMIME 解码器管道组件属性中的**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="2725d-117">Configure the MIME/SMIME Decoder pipeline component properties in the **Properties** window.</span></span> <span data-ttu-id="2725d-118">有关 MIME/SMIME 解码器的详细信息，请参阅[如何配置 MIME-SMIME 解码器管道组件](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="2725d-118">For more information about the MIME/SMIME decoder, see [How to Configure the MIME-SMIME Decoder Pipeline Component](../core/how-to-configure-the-mime-smime-decoder-pipeline-component.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="2725d-119">管道部署到 BizTalk 组使用后，可以配置接收位置的管道属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="2725d-119">You can configure pipeline properties for a receive location after the pipeline has been deployed into a BizTalk group using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="2725d-120">每个接收位置在 BizTalk 组中，可以配置不同的管道属性。</span><span class="sxs-lookup"><span data-stu-id="2725d-120">You can configure different pipeline properties for each receive location in the BizTalk group.</span></span> <span data-ttu-id="2725d-121">有关详细信息，请参阅[如何配置每个实例的接收位置的管道属性](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="2725d-121">For more information, see [How to Configure Per-instance Pipeline Properties for a Receive Location](../core/how-to-configure-per-instance-pipeline-properties-for-a-receive-location.md).</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="2725d-122">MIME/SMIME 解码器管道组件执行解密和数字签名验证 （如果配置为执行这两个函数）。</span><span class="sxs-lookup"><span data-stu-id="2725d-122">The MIME/SMIME Decoder pipeline component performs both decryption and digital signature validation (when configured to perform both functions).</span></span> <span data-ttu-id="2725d-123">因此，如果你要配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收加密和签名消息，则可以使用相同的接收管道。</span><span class="sxs-lookup"><span data-stu-id="2725d-123">Therefore, if you are configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to receive encrypted and signed messages, you can use the same receive pipeline.</span></span> <span data-ttu-id="2725d-124">换而言之，不需要创建单独的管道解密和数字签名验证。</span><span class="sxs-lookup"><span data-stu-id="2725d-124">In other words, you do not have to create separate pipelines for decryption and digital signature validation.</span></span>  
  
3. <span data-ttu-id="2725d-125">生成并部署接收管道。</span><span class="sxs-lookup"><span data-stu-id="2725d-125">Build and deploy the receive pipeline.</span></span>  
  
### <a name="to-configure-the-receive-location-for-receiving-signed-messages"></a><span data-ttu-id="2725d-126">若要配置接收位置以便接收签名消息</span><span class="sxs-lookup"><span data-stu-id="2725d-126">To configure the receive location for receiving signed messages</span></span>  
  
1.  <span data-ttu-id="2725d-127">BizTalk 将添加到包括接收位置接收到 BizTalk 应用程序的上一个过程中创建程序集签名消息。</span><span class="sxs-lookup"><span data-stu-id="2725d-127">Add the BizTalk assembly that you created in previous procedure to the BizTalk Application including the receive locations to receive signed messages.</span></span> <span data-ttu-id="2725d-128">有关如何添加 BizTalk 程序集的详细信息，请参阅[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="2725d-128">For more information about how to add BizTalk assemblies, see [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
2.  <span data-ttu-id="2725d-129">在上一过程中创建的接收管道在 BizTalk 应用程序中配置的接收位置。</span><span class="sxs-lookup"><span data-stu-id="2725d-129">Configure the receive locations in the BizTalk Application with the receive pipeline that you created in previous procedure.</span></span> <span data-ttu-id="2725d-130">详细了解如何配置接收位置，请参阅[如何编辑接收位置属性](../core/how-to-edit-the-properties-of-a-receive-location.md)。</span><span class="sxs-lookup"><span data-stu-id="2725d-130">For more information about how to configure receive locations, see [How to Edit the Properties of a Receive Location](../core/how-to-edit-the-properties-of-a-receive-location.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2725d-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="2725d-131">See Also</span></span>  
 <span data-ttu-id="2725d-132">[BizTalk Server 用于签名消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="2725d-132">[Certificates that BizTalk Server Uses for Signed Messages](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span></span>  
 <span data-ttu-id="2725d-133">[如何配置 BizTalk Server 以便发送签名消息](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="2725d-133">[How to Configure BizTalk Server for Sending Signed Messages](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md) </span></span>  
 <span data-ttu-id="2725d-134">[对消息的发件人进行身份验证](../core/authenticating-the-sender-of-a-message.md) </span><span class="sxs-lookup"><span data-stu-id="2725d-134">[Authenticating the Sender of a Message](../core/authenticating-the-sender-of-a-message.md) </span></span>  
 [<span data-ttu-id="2725d-135">发送和接收签名消息</span><span class="sxs-lookup"><span data-stu-id="2725d-135">Sending and Receiving Signed Messages</span></span>](../core/sending-and-receiving-signed-messages.md)