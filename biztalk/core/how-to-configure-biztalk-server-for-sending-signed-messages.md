---
title: "如何将 BizTalk Server 配置为发送注册消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: be86fbb3-de80-4d9f-bcf0-c61347704229
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7ef71f5c11d6c1a000369644b822aa9f4d4ef792
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-biztalk-server-for-sending-signed-messages"></a><span data-ttu-id="c09a2-102">如何配置 BizTalk Server 以便发送签名消息</span><span class="sxs-lookup"><span data-stu-id="c09a2-102">How to Configure BizTalk Server for Sending Signed Messages</span></span>
<span data-ttu-id="c09a2-103">以下过程列出了配置 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 以便发送签名消息需遵守的步骤。</span><span class="sxs-lookup"><span data-stu-id="c09a2-103">The following procedure lists the steps that you have to follow to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send signed messages.</span></span>  
  
-   <span data-ttu-id="c09a2-104">创建管道以便发送签名消息</span><span class="sxs-lookup"><span data-stu-id="c09a2-104">To create a pipeline to send signed messages</span></span>  
  
-   <span data-ttu-id="c09a2-105">配置用于发送签名消息的发送端口</span><span class="sxs-lookup"><span data-stu-id="c09a2-105">To configure the send port for sending signed messages</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="c09a2-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="c09a2-106">Prerequisites</span></span>  
 <span data-ttu-id="c09a2-107">在配置之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s 针对发送签名的消息，你必须执行中的步骤[如何安装进行数字签名的证书](../core/how-to-install-the-certificates-for-digital-signatures.md)。</span><span class="sxs-lookup"><span data-stu-id="c09a2-107">Before configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s for sending signed messages, you must perform the steps in [How to install the Certificates for Digital Signatures](../core/how-to-install-the-certificates-for-digital-signatures.md).</span></span>  
  
### <a name="to-create-a-pipeline-to-send-signed-messages"></a><span data-ttu-id="c09a2-108">创建管道以便发送签名消息</span><span class="sxs-lookup"><span data-stu-id="c09a2-108">To create a pipeline to send signed messages</span></span>  
  
1.  <span data-ttu-id="c09a2-109">在 Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的解决方案资源管理器中，选择要在其中创建管道的项目。</span><span class="sxs-lookup"><span data-stu-id="c09a2-109">In Solution Explorer in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], select the project in which you want to create the pipeline.</span></span>  
  
    1.  <span data-ttu-id="c09a2-110">上**文件**菜单上，单击**添加新项**。</span><span class="sxs-lookup"><span data-stu-id="c09a2-110">On the **File** menu, click **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="c09a2-111">在**添加新项**对话框框中，展开 BizTalk 项目项，单击**管道文件**，然后单击**发送管道**模板。</span><span class="sxs-lookup"><span data-stu-id="c09a2-111">In the **Add New Item** dialog box, expand BizTalk Project Items, click **Pipeline Files**, and then click the **Send Pipeline** template.</span></span>  
  
    3.  <span data-ttu-id="c09a2-112">在**名称**字段中，键入管道的名称。</span><span class="sxs-lookup"><span data-stu-id="c09a2-112">In the **Name** field, type a name for the pipeline.</span></span>  
  
    4.  <span data-ttu-id="c09a2-113">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="c09a2-113">Click **Add**.</span></span>  
  
         <span data-ttu-id="c09a2-114">此时，新的管道将显示在解决方案资源管理器中。</span><span class="sxs-lookup"><span data-stu-id="c09a2-114">The new pipeline appears in Solution Explorer.</span></span>  
  
2.  <span data-ttu-id="c09a2-115">将 MIME/SMIME 编码器管道组件拖至接收管道的编码阶段。</span><span class="sxs-lookup"><span data-stu-id="c09a2-115">Drag the MIME/SMIME Encoder pipeline component into the Encode stage of a receive pipeline.</span></span>  
  
     <span data-ttu-id="c09a2-116">![MIME &#47;SMIME 编码器管道组件](../core/media/bts-dev-mimesmimeencoder.gif "BTS_DEV_MIMESMIMEEncoder")</span><span class="sxs-lookup"><span data-stu-id="c09a2-116">![MIME&#47;SMIME Encoder pipeline component](../core/media/bts-dev-mimesmimeencoder.gif "BTS_DEV_MIMESMIMEEncoder")</span></span>  
  
3.  <span data-ttu-id="c09a2-117">在属性窗口中，将配置 MIME/SMIME 编码器管道组件**签名类型**属性**ClearSign**或**BlobSign**。</span><span class="sxs-lookup"><span data-stu-id="c09a2-117">In the Properties window, configure the MIME/SMIME Encoder pipeline component **Signature type** property to **ClearSign**or **BlobSign**.</span></span> <span data-ttu-id="c09a2-118">有关详细信息**启用加密**属性，请参阅[如何配置 MIME SMIME 编码器管道组件](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="c09a2-118">For more information about the **Enable encryption** property, see [How to Configure the MIME-SMIME Encoder Pipeline Component](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md).</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="c09a2-119">如果你使用加密，你可以只选择**BlobSign**。</span><span class="sxs-lookup"><span data-stu-id="c09a2-119">If you are also using encryption, you can only select **BlobSign**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c09a2-120">您可以在将管道部署到某一 BizTalk 组中后使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置发送管道组件属性。</span><span class="sxs-lookup"><span data-stu-id="c09a2-120">You can configure the send pipeline component properties using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console after the pipeline has been deployed into a BizTalk group.</span></span> <span data-ttu-id="c09a2-121">有关详细信息，请参阅[如何配置每个实例管道发送端口属性](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="c09a2-121">For more information, see [How to Configure Per-Instance Pipeline Properties for a Send Port](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c09a2-122">MIME/SMIME 编码器管道组件既执行加密，又执行数字签名（在配置为执行这两个功能时）。</span><span class="sxs-lookup"><span data-stu-id="c09a2-122">The MIME/SMIME Encoder pipeline component performs both encryption and digital signing (when configured to perform both functions).</span></span> <span data-ttu-id="c09a2-123">因此，如果将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置为发送加密和签名消息，则可以使用同一发送管道。</span><span class="sxs-lookup"><span data-stu-id="c09a2-123">Therefore, if you are configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send encrypted and signed messages, you can use the same send pipeline.</span></span> <span data-ttu-id="c09a2-124">换言之，您不必为加密和数字签名创建各自的管道。</span><span class="sxs-lookup"><span data-stu-id="c09a2-124">In other words, you do not have to create separate pipelines for encryption and digital signing.</span></span>  
  
4.  <span data-ttu-id="c09a2-125">生成并部署发送管道。</span><span class="sxs-lookup"><span data-stu-id="c09a2-125">Build and deploy the send pipeline.</span></span>  
  
### <a name="to-configure-the-send-port-for-sending-signed-messages"></a><span data-ttu-id="c09a2-126">配置用于发送签名消息的发送端口</span><span class="sxs-lookup"><span data-stu-id="c09a2-126">To configure the send port for sending signed messages</span></span>  
  
1.  <span data-ttu-id="c09a2-127">将您在前面过程中创建的 BizTalk 程序集添加到包括接收位置的 BizTalk 应用程序，以便发送签名消息。</span><span class="sxs-lookup"><span data-stu-id="c09a2-127">Add the BizTalk assembly that you created in previous procedure to the BizTalk Application including the receive locations to sending signed messages.</span></span> <span data-ttu-id="c09a2-128">有关如何添加 BizTalk 程序集的详细信息，请参阅[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="c09a2-128">For more information about how to add BizTalk assemblies, see [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
2.  <span data-ttu-id="c09a2-129">使用您在前面过程中创建的发送管道配置 BizTalk 应用程序中的发送端口。</span><span class="sxs-lookup"><span data-stu-id="c09a2-129">Configure the send port in the BizTalk Application with the send pipeline that you created in previous procedure.</span></span> <span data-ttu-id="c09a2-130">有关如何配置发送端口的详细信息，请参阅[创建和配置发送端口](../core/creating-and-configuring-send-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="c09a2-130">For more information about how to configure send ports, see [Creating and Configuring Send Ports](../core/creating-and-configuring-send-ports.md).</span></span>  
  
3.  <span data-ttu-id="c09a2-131">配置 BizTalk 组中安装签名证书[如何安装进行数字签名的证书](../core/how-to-install-the-certificates-for-digital-signatures.md)。</span><span class="sxs-lookup"><span data-stu-id="c09a2-131">Configure the BizTalk group with the signing certificate that you installed in [How to install the Certificates for Digital Signatures](../core/how-to-install-the-certificates-for-digital-signatures.md).</span></span> <span data-ttu-id="c09a2-132">有关详细信息如何配置 BizTalk 组，请参阅[如何修改组属性](../core/how-to-modify-group-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="c09a2-132">For more information how to configure a BizTalk group, see [How to Modify Group Properties](../core/how-to-modify-group-properties.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c09a2-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c09a2-133">See Also</span></span>  
 <span data-ttu-id="c09a2-134">[如何将 BizTalk Server 配置为接收注册消息](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="c09a2-134">[How to Configure BizTalk Server for Receiving Signed Messages](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md) </span></span>  
 <span data-ttu-id="c09a2-135">[BizTalk Server 用于签名的消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="c09a2-135">[Certificates that BizTalk Server Uses for Signed Messages](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span></span>  
 [<span data-ttu-id="c09a2-136">发送和接收签名消息</span><span class="sxs-lookup"><span data-stu-id="c09a2-136">Sending and Receiving Signed Messages</span></span>](../core/sending-and-receiving-signed-messages.md)