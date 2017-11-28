---
title: "如何配置 BizTalk 服务器以接收注册 MIME 或 SMIME 消息 |Microsoft 文档"
ms.custom: 
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50570257-7bb6-4ede-9026-873eefd06483
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 88487fb96c89b8a611ab591223fa1820f70de1cd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-biztalk-server-to-receive-signed-mime-or-smime-messages"></a><span data-ttu-id="e0ab5-102">如何配置 BizTalk 服务器以接收注册 MIME 或 SMIME 消息</span><span class="sxs-lookup"><span data-stu-id="e0ab5-102">How to Configure BizTalk Server to Receive Signed MIME or SMIME Messages</span></span>
<span data-ttu-id="e0ab5-103">本主题介绍如何配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用证书来接收签名的 MIME/SMIME 消息。</span><span class="sxs-lookup"><span data-stu-id="e0ab5-103">This topic describes how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use certificates to receive signed MIME/SMIME messages.</span></span> <span data-ttu-id="e0ab5-104">下面的过程也适用于配置的签名的消息接收通过 AS2 传输。</span><span class="sxs-lookup"><span data-stu-id="e0ab5-104">The procedure below also applies to configuring the receiving of signed messages over AS2 transport.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e0ab5-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="e0ab5-105">Prerequisites</span></span>  
 <span data-ttu-id="e0ab5-106">若要执行本主题中的过程，你必须登录为的成员[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理员组。</span><span class="sxs-lookup"><span data-stu-id="e0ab5-106">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-biztalk-server-to-receive-signed-messages"></a><span data-ttu-id="e0ab5-107">若要配置 BizTalk 服务器以接收签名消息</span><span class="sxs-lookup"><span data-stu-id="e0ab5-107">To configure BizTalk Server to receive signed messages</span></span>  
  
1.  <span data-ttu-id="e0ab5-108">创建管道用于接收签名的消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e0ab5-108">Create a pipeline to receive signed messages, as follows:</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e0ab5-109">配置 AS2 传输，对于接收已签名消息，因为 AS2Receive 和 AS2EdiReceive 管道，都将纳入时，此步骤不需要[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供此函数。</span><span class="sxs-lookup"><span data-stu-id="e0ab5-109">This step is not necessary when configuring AS2 transport for receiving signed messages because the AS2Receive and AS2EdiReceive pipelines that are included in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] serve this function.</span></span>  
  
    1.  <span data-ttu-id="e0ab5-110">创建接收管道，然后拖动到接收管道则解码阶段的 MIME/SMIME 解码器管道组件。</span><span class="sxs-lookup"><span data-stu-id="e0ab5-110">Create a receive pipeline and then drag the MIME/SMIME Decoder pipeline component into the Decode stage of the receive pipeline.</span></span>  
  
    2.  <span data-ttu-id="e0ab5-111">在**属性**窗口中，配置的 MIME/SMIME 解码器管道组件属性。</span><span class="sxs-lookup"><span data-stu-id="e0ab5-111">In the **Properties** window, configure the MIME/SMIME Decoder pipeline component properties.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="e0ab5-112">您可以在将管道部署到某一 BizTalk 组中后，使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置接收位置的管道属性。</span><span class="sxs-lookup"><span data-stu-id="e0ab5-112">You can configure pipeline properties for a receive location after the pipeline has been deployed into a BizTalk group using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="e0ab5-113">还可以为 BizTalk 组中的每个接收位置配置不同的管道属性。</span><span class="sxs-lookup"><span data-stu-id="e0ab5-113">You can configure different pipeline properties for each receive location in the BizTalk group.</span></span>  
  
    3.  <span data-ttu-id="e0ab5-114">生成并部署接收管道。</span><span class="sxs-lookup"><span data-stu-id="e0ab5-114">Build and deploy the receive pipeline.</span></span>  
  
2.  <span data-ttu-id="e0ab5-115">配置接收位置接收签名的消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e0ab5-115">Configure a receive location for receiving signed messages, as follows:</span></span>  
  
    1.  <span data-ttu-id="e0ab5-116">添加你创建包含 BizTalk 应用程序包括接收位置接收签名的消息的接收管道的 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="e0ab5-116">Add the BizTalk assembly that you created containing the receive pipeline to the BizTalk application including the receive locations to receive signed messages.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="e0ab5-117">对于接收已签名消息，由于 AS2Receive 和 AS2EdiReceive 管道都包括 BizTalk EDI 应用程序中配置 AS2 传输时不需要此步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e0ab5-117">This step is not necessary when configuring AS2 transport for receiving signed messages because the AS2Receive and AS2EdiReceive pipelines are included in the BizTalk EDI Application in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
    2.  <span data-ttu-id="e0ab5-118">配置你在前面的过程中创建接收管道的 BizTalk 应用程序中的接收位置。</span><span class="sxs-lookup"><span data-stu-id="e0ab5-118">Configure the receive locations in the BizTalk application with the receive pipeline that you created in previous procedure.</span></span>  
  
3.  <span data-ttu-id="e0ab5-119">配置当事方，并且接收签名的消息，如下所示的证书：</span><span class="sxs-lookup"><span data-stu-id="e0ab5-119">Configure the party with a certificate for receiving signed messages, as follows:</span></span>  
  
    -   <span data-ttu-id="e0ab5-120">打开**参与方属性**对话框在 BizTalk Server 管理控制台中，单击**证书**选项卡上，单击**浏览**，选择相应的证书，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e0ab5-120">Open the **Party Properties** dialog box in the BizTalk Server Administration Console, click the **Certificate** tab, click **Browse**, select the appropriate certificate, and then click **OK**.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="e0ab5-121">用于验证参与方签名的证书必须与用于验证其他参与方签名的证书不同。</span><span class="sxs-lookup"><span data-stu-id="e0ab5-121">The certificate used to verify a signature for a party must be unique from the certificates used to verify signatures for other parties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0ab5-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0ab5-122">See Also</span></span>  
 [<span data-ttu-id="e0ab5-123">为 MIME 或 SMIME 消息配置证书</span><span class="sxs-lookup"><span data-stu-id="e0ab5-123">Configuring Certificates for MIME or SMIME Messages</span></span>](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)