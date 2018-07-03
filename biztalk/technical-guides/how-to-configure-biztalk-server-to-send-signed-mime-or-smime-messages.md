---
title: 如何配置 BizTalk Server 发送到签名的 MIME 或 SMIME 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ba42463b-2c12-4329-919e-aca427d14eee
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5e1f3e01179f26c825480bb3a7de8d13b8539129
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005462"
---
# <a name="how-to-configure-biztalk-server-to-send-signed-mime-or-smime-messages"></a><span data-ttu-id="cf707-102">如何配置 BizTalk Server 以便发送签名的 MIME 或 SMIME 消息</span><span class="sxs-lookup"><span data-stu-id="cf707-102">How to Configure BizTalk Server to Send Signed MIME or SMIME Messages</span></span>
<span data-ttu-id="cf707-103">本主题介绍如何配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以使用证书进行签名的 MIME/SMIME 消息发送。</span><span class="sxs-lookup"><span data-stu-id="cf707-103">This topic describes how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use certificates to send signed MIME/SMIME messages.</span></span> <span data-ttu-id="cf707-104">下面的过程也适用于配置通过 AS2 传输发送签名消息。</span><span class="sxs-lookup"><span data-stu-id="cf707-104">The procedure below also applies to configuring the sending of signed messages over AS2 transport.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="cf707-105">必要條件</span><span class="sxs-lookup"><span data-stu-id="cf707-105">Prerequisites</span></span>  
 <span data-ttu-id="cf707-106">若要执行本主题中的过程，您必须登录以成员的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="cf707-106">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-biztalk-server-to-send-signed-messages"></a><span data-ttu-id="cf707-107">若要配置 BizTalk Server 以便发送签名的消息</span><span class="sxs-lookup"><span data-stu-id="cf707-107">To configure BizTalk Server to send signed messages</span></span>  
  
1. <span data-ttu-id="cf707-108">创建一个管道以发送签名的消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf707-108">Create a pipeline to send signed messages, as follows:</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="cf707-109">在配置 AS2 传输以便发送签名的消息，因为 AS2Send 和 AS2EdiSend 管道，包括在不需要执行此步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供此函数。</span><span class="sxs-lookup"><span data-stu-id="cf707-109">This step is not necessary when configuring AS2 transport for sending signed messages because the AS2Send and AS2EdiSend pipelines that are included in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] serve this function.</span></span>  
  
   1. <span data-ttu-id="cf707-110">创建一个发送管道，然后将 MIME/SMIME 编码器管道组件拖至管道的编码阶段。</span><span class="sxs-lookup"><span data-stu-id="cf707-110">Create a send pipeline and then drag the MIME/SMIME Encoder pipeline component into the Encode stage of the pipeline.</span></span>  
  
   2. <span data-ttu-id="cf707-111">在中**属性**窗口中，配置到 ClearSign 或 BlobSign 的 MIME/SMIME 编码器管道组件签名类型属性。</span><span class="sxs-lookup"><span data-stu-id="cf707-111">In the **Properties** window, configure the MIME/SMIME Encoder pipeline component Signature type property to ClearSign or BlobSign.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="cf707-112">如果您使用加密，只能选择 BlobSign。</span><span class="sxs-lookup"><span data-stu-id="cf707-112">If you are also using encryption, you can only select BlobSign.</span></span>  
      > 
      > [!NOTE]
      >  <span data-ttu-id="cf707-113">您可以在将管道部署到某一 BizTalk 组中后使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置发送管道组件属性。</span><span class="sxs-lookup"><span data-stu-id="cf707-113">You can configure the send pipeline component properties using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console after the pipeline has been deployed into a BizTalk group.</span></span>  
      > 
      > [!NOTE]
      >  <span data-ttu-id="cf707-114">MIME/SMIME 编码器管道组件既执行加密，又执行数字签名（在配置为执行这两个功能时）。</span><span class="sxs-lookup"><span data-stu-id="cf707-114">The MIME/SMIME Encoder pipeline component performs both encryption and digital signing (when configured to perform both functions).</span></span> <span data-ttu-id="cf707-115">因此，如果将 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 配置为发送加密和签名消息，则可以使用同一发送管道。</span><span class="sxs-lookup"><span data-stu-id="cf707-115">Therefore, if you are configuring [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to send encrypted and signed messages, you can use the same send pipeline.</span></span> <span data-ttu-id="cf707-116">换言之，您不必为加密和数字签名创建各自的管道。</span><span class="sxs-lookup"><span data-stu-id="cf707-116">In other words, you do not have to create separate pipelines for encryption and digital signing.</span></span>  
  
   3. <span data-ttu-id="cf707-117">生成并部署发送管道。</span><span class="sxs-lookup"><span data-stu-id="cf707-117">Build and deploy the send pipeline.</span></span>  
  
2. <span data-ttu-id="cf707-118">配置发送端口以便发送签名的消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="cf707-118">Configure the send port for sending signed messages, as follows:</span></span>  
  
   1. <span data-ttu-id="cf707-119">添加你创建包含包括发送端口以发送签名的消息的 BizTalk 应用程序的发送管道的 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="cf707-119">Add the BizTalk assembly that you created containing the send pipeline to the BizTalk application that includes the send ports to send signed messages.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="cf707-120">因为 AS2Send 和 AS2EdiSend 管道包含在 BizTalk EDI 应用程序中配置 AS2 传输发送签名消息时不需要执行此步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cf707-120">This step is not necessary when configuring AS2 transport for sending signed messages because the AS2Send and AS2EdiSend pipelines are included in the BizTalk EDI Application in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
   2. <span data-ttu-id="cf707-121">在上一过程中创建的发送管道的 BizTalk 应用程序中配置发送端口。</span><span class="sxs-lookup"><span data-stu-id="cf707-121">Configure the send port in the BizTalk application with the send pipeline that you created in the previous procedure.</span></span>  
  
3. <span data-ttu-id="cf707-122">配置组，如下所示发送签名的消息的证书：</span><span class="sxs-lookup"><span data-stu-id="cf707-122">Configure the group with a certificate for sending signed messages, as follows:</span></span>  
  
   1. <span data-ttu-id="cf707-123">配置 BizTalk 组的情况下展开 BizTalk 组中的安装签名证书[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，右击**BizTalk 组**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="cf707-123">Configure the BizTalk group with the signing certificate that you installed by expanding the BizTalk group in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration Console, right-clicking **BizTalk Group**, and then clicking **Properties**.</span></span>  
  
   2. <span data-ttu-id="cf707-124">单击证书选项卡中，单击**浏览**，选择相应的证书，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="cf707-124">Click the Certificate tab, click **Browse**, select the appropriate certificate, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf707-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf707-125">See Also</span></span>  
 [<span data-ttu-id="cf707-126">为 MIME 或 SMIME 消息配置证书</span><span class="sxs-lookup"><span data-stu-id="cf707-126">Configuring Certificates for MIME or SMIME Messages</span></span>](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)