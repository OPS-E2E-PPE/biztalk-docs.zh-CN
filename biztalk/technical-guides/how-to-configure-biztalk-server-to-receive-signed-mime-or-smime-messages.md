---
title: 如何配置 BizTalk Server 以便接收签名的 MIME 或 SMIME 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/29/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 50570257-7bb6-4ede-9026-873eefd06483
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2df073a27cb9e17851c9afec4b5531424d913fab
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37009182"
---
# <a name="how-to-configure-biztalk-server-to-receive-signed-mime-or-smime-messages"></a><span data-ttu-id="6f5d5-102">如何配置 BizTalk Server 以便接收签名的 MIME 或 SMIME 消息</span><span class="sxs-lookup"><span data-stu-id="6f5d5-102">How to Configure BizTalk Server to Receive Signed MIME or SMIME Messages</span></span>
<span data-ttu-id="6f5d5-103">本主题介绍如何配置[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用证书以接收签名的 MIME/SMIME 消息。</span><span class="sxs-lookup"><span data-stu-id="6f5d5-103">This topic describes how to configure [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use certificates to receive signed MIME/SMIME messages.</span></span> <span data-ttu-id="6f5d5-104">下面的过程也适用于配置的签名消息接收通过 AS2 传输。</span><span class="sxs-lookup"><span data-stu-id="6f5d5-104">The procedure below also applies to configuring the receiving of signed messages over AS2 transport.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6f5d5-105">必要條件</span><span class="sxs-lookup"><span data-stu-id="6f5d5-105">Prerequisites</span></span>  
 <span data-ttu-id="6f5d5-106">若要执行本主题中的过程，您必须登录以成员的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Administrators 组。</span><span class="sxs-lookup"><span data-stu-id="6f5d5-106">To perform the procedure in this topic, you must be logged on as a member of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administrators group.</span></span>  
  
### <a name="to-configure-biztalk-server-to-receive-signed-messages"></a><span data-ttu-id="6f5d5-107">若要配置 BizTalk Server 以便接收签名消息</span><span class="sxs-lookup"><span data-stu-id="6f5d5-107">To configure BizTalk Server to receive signed messages</span></span>  
  
1. <span data-ttu-id="6f5d5-108">创建一个管道以接收签名的消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6f5d5-108">Create a pipeline to receive signed messages, as follows:</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="6f5d5-109">在配置 AS2 传输，用于接收签名消息，因为 AS2Receive 和 AS2EdiReceive 管道，包括在不需要执行此步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供此函数。</span><span class="sxs-lookup"><span data-stu-id="6f5d5-109">This step is not necessary when configuring AS2 transport for receiving signed messages because the AS2Receive and AS2EdiReceive pipelines that are included in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] serve this function.</span></span>  
  
   1. <span data-ttu-id="6f5d5-110">创建一个接收管道，然后将 MIME/SMIME 解码器管道组件拖至接收管道的解码阶段。</span><span class="sxs-lookup"><span data-stu-id="6f5d5-110">Create a receive pipeline and then drag the MIME/SMIME Decoder pipeline component into the Decode stage of the receive pipeline.</span></span>  
  
   2. <span data-ttu-id="6f5d5-111">在中**属性**窗口中，配置 MIME/SMIME 解码器管道组件属性。</span><span class="sxs-lookup"><span data-stu-id="6f5d5-111">In the **Properties** window, configure the MIME/SMIME Decoder pipeline component properties.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="6f5d5-112">您可以在将管道部署到某一 BizTalk 组中后，使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台配置接收位置的管道属性。</span><span class="sxs-lookup"><span data-stu-id="6f5d5-112">You can configure pipeline properties for a receive location after the pipeline has been deployed into a BizTalk group using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="6f5d5-113">还可以为 BizTalk 组中的每个接收位置配置不同的管道属性。</span><span class="sxs-lookup"><span data-stu-id="6f5d5-113">You can configure different pipeline properties for each receive location in the BizTalk group.</span></span>  
  
   3. <span data-ttu-id="6f5d5-114">生成并部署接收管道。</span><span class="sxs-lookup"><span data-stu-id="6f5d5-114">Build and deploy the receive pipeline.</span></span>  
  
2. <span data-ttu-id="6f5d5-115">配置接收位置以便接收签名的消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6f5d5-115">Configure a receive location for receiving signed messages, as follows:</span></span>  
  
   1. <span data-ttu-id="6f5d5-116">添加你创建包含到包括接收位置的 BizTalk 应用程序以接收签名的消息的接收管道的 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="6f5d5-116">Add the BizTalk assembly that you created containing the receive pipeline to the BizTalk application including the receive locations to receive signed messages.</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="6f5d5-117">对于接收已签名消息，因为 AS2Receive 和 AS2EdiReceive 管道包含在 BizTalk EDI 应用程序中配置 AS2 传输时不需要执行此步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6f5d5-117">This step is not necessary when configuring AS2 transport for receiving signed messages because the AS2Receive and AS2EdiReceive pipelines are included in the BizTalk EDI Application in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>  
  
   2. <span data-ttu-id="6f5d5-118">在前面过程中创建的接收管道的 BizTalk 应用程序中配置接收位置。</span><span class="sxs-lookup"><span data-stu-id="6f5d5-118">Configure the receive locations in the BizTalk application with the receive pipeline that you created in previous procedure.</span></span>  
  
3. <span data-ttu-id="6f5d5-119">配置参与方，并且证书以便接收签名的消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6f5d5-119">Configure the party with a certificate for receiving signed messages, as follows:</span></span>  
  
   -   <span data-ttu-id="6f5d5-120">打开**参与方属性**对话框的在 BizTalk Server 管理控制台中，单击**证书**选项卡上，单击**浏览**，选择相应的证书，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6f5d5-120">Open the **Party Properties** dialog box in the BizTalk Server Administration Console, click the **Certificate** tab, click **Browse**, select the appropriate certificate, and then click **OK**.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="6f5d5-121">用于验证参与方签名的证书必须与用于验证其他参与方签名的证书不同。</span><span class="sxs-lookup"><span data-stu-id="6f5d5-121">The certificate used to verify a signature for a party must be unique from the certificates used to verify signatures for other parties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f5d5-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f5d5-122">See Also</span></span>  
 [<span data-ttu-id="6f5d5-123">为 MIME 或 SMIME 消息配置证书</span><span class="sxs-lookup"><span data-stu-id="6f5d5-123">Configuring Certificates for MIME or SMIME Messages</span></span>](../technical-guides/configuring-certificates-for-mime-or-smime-messages.md)