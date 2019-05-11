---
title: 如何配置 BizTalk Server 以便发送加密消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb751d7c-49cd-46f0-9630-254cf06c497e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c91bd408fc9fcded963ca3f8c9fb03260915236
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386286"
---
# <a name="how-to-configure-biztalk-server-for-sending-encrypted-messages"></a><span data-ttu-id="136d8-102">如何配置 BizTalk Server 以便发送加密的消息</span><span class="sxs-lookup"><span data-stu-id="136d8-102">How to Configure BizTalk Server for Sending Encrypted Messages</span></span>
<span data-ttu-id="136d8-103">以下过程列出了您必须按照配置的步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以便发送加密的消息。</span><span class="sxs-lookup"><span data-stu-id="136d8-103">The following procedure lists the steps that you have to follow to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send encrypted messages.</span></span>  
  
-   <span data-ttu-id="136d8-104">若要创建管道以便发送加密的消息</span><span class="sxs-lookup"><span data-stu-id="136d8-104">To create a pipeline to send encrypted messages</span></span>  
  
-   <span data-ttu-id="136d8-105">若要配置用于发送加密的消息的发送端口</span><span class="sxs-lookup"><span data-stu-id="136d8-105">To configure the send port for sending encrypted messages</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="136d8-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="136d8-106">Prerequisites</span></span>  
 <span data-ttu-id="136d8-107">配置之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以便发送加密的消息，必须首先执行中的步骤[如何为加密消息安装证书](../core/how-to-install-the-certificates-for-encrypted-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="136d8-107">Before configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]s for sending encrypted messages, you must perform the steps in [How to Install the Certificates for Encrypted Messages](../core/how-to-install-the-certificates-for-encrypted-messages.md).</span></span>  
  
### <a name="to-create-a-pipeline-to-send-encrypted-messages"></a><span data-ttu-id="136d8-108">若要创建管道以便发送加密的消息</span><span class="sxs-lookup"><span data-stu-id="136d8-108">To create a pipeline to send encrypted messages</span></span>  
  
1. <span data-ttu-id="136d8-109">在解决方案资源管理器在 microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，选择想要创建管道的项目。</span><span class="sxs-lookup"><span data-stu-id="136d8-109">In Solution Explorer in the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], select the project in which you want to create the pipeline.</span></span>  
  
   1.  <span data-ttu-id="136d8-110">上**文件**菜单上，单击**添加新项**。</span><span class="sxs-lookup"><span data-stu-id="136d8-110">On the **File** menu, click **Add New Item**.</span></span>  
  
   2.  <span data-ttu-id="136d8-111">在中**添加新项**对话框框中，展开 BizTalk 项目项，单击**管道文件**，然后单击**发送管道**模板。</span><span class="sxs-lookup"><span data-stu-id="136d8-111">In the **Add New Item** dialog box, expand BizTalk Project Items, click **Pipeline Files**, and then click the **Send Pipeline** template.</span></span>  
  
   3.  <span data-ttu-id="136d8-112">在中**名称**字段中，键入管道的名称。</span><span class="sxs-lookup"><span data-stu-id="136d8-112">In the **Name** field, type a name for the pipeline.</span></span>  
  
   4.  <span data-ttu-id="136d8-113">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="136d8-113">Click **Add**.</span></span>  
  
        <span data-ttu-id="136d8-114">在解决方案资源管理器中将显示新的管道。</span><span class="sxs-lookup"><span data-stu-id="136d8-114">The new pipeline appears in Solution Explorer.</span></span>  
  
2. <span data-ttu-id="136d8-115">将 MIME/SMIME 编码器管道组件拖至接收管道的编码阶段。</span><span class="sxs-lookup"><span data-stu-id="136d8-115">Drag the MIME/SMIME Encoder pipeline component into the Encode stage of a receive pipeline.</span></span>  
  
    <span data-ttu-id="136d8-116">![MIME&#47;SMIME 编码器管道组件](../core/media/bts-dev-mimesmimeencoder.gif "BTS_DEV_MIMESMIMEEncoder")</span><span class="sxs-lookup"><span data-stu-id="136d8-116">![MIME&#47;SMIME Encoder pipeline component](../core/media/bts-dev-mimesmimeencoder.gif "BTS_DEV_MIMESMIMEEncoder")</span></span>  
  
   -   <span data-ttu-id="136d8-117">在属性窗口中配置 MIME/SMIME 编码器管道组件**启用加密**属性设置为`True`。</span><span class="sxs-lookup"><span data-stu-id="136d8-117">In the Properties window, configure the MIME/SMIME Encoder pipeline component **Enable encryption** property to `True`.</span></span> <span data-ttu-id="136d8-118">有关详细信息**启用加密**属性，请参阅[如何配置 MIME-SMIME 编码器管道组件](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="136d8-118">For more information about the **Enable encryption** property, see [How to Configure the MIME-SMIME Encoder Pipeline Component](../core/how-to-configure-the-mime-smime-encoder-pipeline-component.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="136d8-119">可以配置使用的发送管道组件属性[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管道部署到 BizTalk 组后的管理控制台。</span><span class="sxs-lookup"><span data-stu-id="136d8-119">You can configure the send pipeline component properties using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console after the pipeline has been deployed into a BizTalk group.</span></span> <span data-ttu-id="136d8-120">有关详细信息，请参阅[如何为发送端口配置每个实例的管道属性](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="136d8-120">For more information, see [How to Configure Per-Instance Pipeline Properties for a Send Port](../core/how-to-configure-per-instance-pipeline-properties-for-a-send-port.md).</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="136d8-121">MIME/SMIME 编码器管道组件执行加密和数字签名 （如果配置为执行这两个函数）。</span><span class="sxs-lookup"><span data-stu-id="136d8-121">The MIME/SMIME Encoder pipeline component performs both encryption and digital signing (when configured to perform both functions).</span></span> <span data-ttu-id="136d8-122">因此，如果你要配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到发送加密和签名消息，则可以使用同一发送管道。</span><span class="sxs-lookup"><span data-stu-id="136d8-122">Therefore, if you are configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send encrypted and signed messages, you can use the same send pipeline.</span></span> <span data-ttu-id="136d8-123">换而言之，不需要创建单独的加密和数字签名的管道。</span><span class="sxs-lookup"><span data-stu-id="136d8-123">In other words, you do not have to create separate pipelines for encryption and digital signing.</span></span>  
  
3. <span data-ttu-id="136d8-124">生成并部署发送管道。</span><span class="sxs-lookup"><span data-stu-id="136d8-124">Build and deploy the send pipeline.</span></span>  
  
### <a name="to-configure-the-send-port-for-sending-encrypted-messages"></a><span data-ttu-id="136d8-125">若要配置用于发送加密的消息的发送端口</span><span class="sxs-lookup"><span data-stu-id="136d8-125">To configure the send port for sending encrypted messages</span></span>  
  
1.  <span data-ttu-id="136d8-126">将添加到包括发送端口的 BizTalk 应用程序以便发送加密的消息的上一个过程中创建的 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="136d8-126">Add the BizTalk assembly that you created in previous procedure to the BizTalk Application including the send ports to send encrypted messages.</span></span> <span data-ttu-id="136d8-127">有关如何添加 BizTalk 程序集的详细信息，请参阅[如何将 BizTalk 程序集添加到应用程序](../core/how-to-add-a-biztalk-assembly-to-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="136d8-127">For more information about how to add BizTalk assemblies, see [How to Add a BizTalk Assembly to an Application](../core/how-to-add-a-biztalk-assembly-to-an-application.md).</span></span>  
  
2.  <span data-ttu-id="136d8-128">在前面过程中创建的发送管道在 BizTalk 应用程序中配置的发送端口，然后将分配中安装的加密证书[如何安装证书用于加密的消息](../core/how-to-install-the-certificates-for-encrypted-messages.md).</span><span class="sxs-lookup"><span data-stu-id="136d8-128">Configure the send port in the BizTalk Application with the send pipeline that you created in previous procedure, and then assign the encryption certificate that you installed in [How to Install the Certificates for Encrypted Messages](../core/how-to-install-the-certificates-for-encrypted-messages.md).</span></span> <span data-ttu-id="136d8-129">有关如何配置发送端口的详细信息，请参阅[如何为发送端口分配证书](../core/how-to-assign-a-certificate-to-a-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="136d8-129">For more information about how to configure send ports, see [How to Assign a Certificate to a Send Port](../core/how-to-assign-a-certificate-to-a-send-port.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="136d8-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="136d8-130">See Also</span></span>  
 <span data-ttu-id="136d8-131">[如何配置 BizTalk Server 以便接收加密的消息](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md) </span><span class="sxs-lookup"><span data-stu-id="136d8-131">[How to Configure BizTalk Server for Receiving Encrypted Messages](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md) </span></span>  
 <span data-ttu-id="136d8-132">[BizTalk Server 用来加密消息的证书](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span><span class="sxs-lookup"><span data-stu-id="136d8-132">[Certificates that BizTalk Server Uses for Encrypted Messages](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span></span>  
 [<span data-ttu-id="136d8-133">发送和接收加密消息</span><span class="sxs-lookup"><span data-stu-id="136d8-133">Sending and Receiving Encrypted Messages</span></span>](../core/sending-and-receiving-encrypted-messages.md)