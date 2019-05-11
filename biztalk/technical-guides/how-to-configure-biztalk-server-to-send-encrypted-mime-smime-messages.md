---
title: 如何配置 BizTalk Server 发送到已加密的 MIME/SMIME 消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 14f67152-5f80-4040-a9d6-0819fab7fcb5
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dded85a219f5a32ce83ebc4da96f0f0566bf8c7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65253383"
---
# <a name="how-to-configure-biztalk-server-to-send-encrypted-mimesmime-messages"></a><span data-ttu-id="8b7ea-102">如何配置 BizTalk Server 以便发送加密的 MIME/SMIME 消息</span><span class="sxs-lookup"><span data-stu-id="8b7ea-102">How to Configure BizTalk Server to Send Encrypted MIME/SMIME Messages</span></span>
<span data-ttu-id="8b7ea-103">本主题介绍如何配置 BizTalk Server 以便使用证书来发送加密的 MIME/SMIME 消息。</span><span class="sxs-lookup"><span data-stu-id="8b7ea-103">This topic describes how to configure BizTalk Server to use certificates to send encrypted MIME/SMIME messages.</span></span> <span data-ttu-id="8b7ea-104">下面的过程也适用于配置通过 AS2 传输发送加密消息。</span><span class="sxs-lookup"><span data-stu-id="8b7ea-104">The procedure below also applies to configuring the sending of encrypted messages over AS2 transport.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8b7ea-105">先决条件</span><span class="sxs-lookup"><span data-stu-id="8b7ea-105">Prerequisites</span></span>  
 <span data-ttu-id="8b7ea-106">若要执行本主题中的过程，必须以 BizTalk Server Administrators 组的成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="8b7ea-106">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-configure-biztalk-server-to-send-encrypted-messages"></a><span data-ttu-id="8b7ea-107">若要配置 BizTalk Server 以便发送加密的消息</span><span class="sxs-lookup"><span data-stu-id="8b7ea-107">To configure BizTalk Server to send encrypted messages</span></span>  
  
1. <span data-ttu-id="8b7ea-108">创建管道以便发送加密的消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8b7ea-108">Create a pipeline to send encrypted messages, as follows:</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="8b7ea-109">在配置 AS2 传输以便发送加密的消息，因为 AS2Send 和 AS2EdiSend 管道，包括在不需要执行此步骤[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供此函数。</span><span class="sxs-lookup"><span data-stu-id="8b7ea-109">This step is not necessary when configuring AS2 transport for sending encrypted messages because the AS2Send and AS2EdiSend pipelines that are included in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] serve this function.</span></span>  
  
   1.  <span data-ttu-id="8b7ea-110">创建一个发送管道，然后将 MIME/SMIME 编码器管道组件拖至管道的编码阶段。</span><span class="sxs-lookup"><span data-stu-id="8b7ea-110">Create a send pipeline and then drag the MIME/SMIME Encoder pipeline component into the Encode stage of the pipeline.</span></span>  
  
   2.  <span data-ttu-id="8b7ea-111">在中**属性**窗口中，配置到的 MIME/SMIME 编码器管道组件启用加密属性**True**。</span><span class="sxs-lookup"><span data-stu-id="8b7ea-111">In the **Properties** window, configure the MIME/SMIME Encoder pipeline component Enable encryption property to **True**.</span></span>  
  
       > [!NOTE]  
       >  <span data-ttu-id="8b7ea-112">可以配置管道部署到 BizTalk 组后，使用 BizTalk Server 管理控制台的发送管道组件属性。</span><span class="sxs-lookup"><span data-stu-id="8b7ea-112">You can configure the send pipeline component properties using the BizTalk Server Administration console after the pipeline has been deployed into a BizTalk group.</span></span>  
  
   3.  <span data-ttu-id="8b7ea-113">生成并部署发送管道。</span><span class="sxs-lookup"><span data-stu-id="8b7ea-113">Build and deploy the send pipeline.</span></span>  
  
2. <span data-ttu-id="8b7ea-114">配置发送端口以便发送加密的消息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8b7ea-114">Configure the send port for sending encrypted messages, as follows:</span></span>  
  
   1.  <span data-ttu-id="8b7ea-115">添加你创建包含到包括接收位置的 BizTalk 应用程序以便接收加密的消息的发送管道的 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="8b7ea-115">Add the BizTalk assembly that you created containing the send pipeline to the BizTalk application including the receive locations to receive encrypted messages.</span></span>  
  
       > [!NOTE]  
       >  <span data-ttu-id="8b7ea-116">配置 AS2 传输以便发送加密的消息，因为 AS2Send 和 AS2EdiSend 管道包含在 BizTalk EDI 应用程序时，不需要此步骤。</span><span class="sxs-lookup"><span data-stu-id="8b7ea-116">This step is not necessary when configuring AS2 transport for sending encrypted messages because the AS2Send and AS2EdiSend pipelines are included in the BizTalk EDI Application.</span></span>  
  
   2.  <span data-ttu-id="8b7ea-117">在上一过程中创建的发送管道在 BizTalk 应用程序中配置的发送端口。</span><span class="sxs-lookup"><span data-stu-id="8b7ea-117">Configure the send port in the BizTalk Application with the send pipeline that you created in the previous procedure.</span></span>  
  
   3.  <span data-ttu-id="8b7ea-118">通过右键单击该发送端口，单击安装的加密证书分配**属性**，然后单击**证书**。</span><span class="sxs-lookup"><span data-stu-id="8b7ea-118">Assign the encryption certificate that you installed by right-clicking the send port, clicking **Properties**, and then clicking **Certificate**.</span></span> <span data-ttu-id="8b7ea-119">单击**浏览**，浏览到你想要将分配到此发送端口，然后单击该证书**确定**。</span><span class="sxs-lookup"><span data-stu-id="8b7ea-119">Click **Browse**, browse to the certificate that you want to assign to this send port, and then click **OK**.</span></span>  
  
       > [!NOTE]  
       >  <span data-ttu-id="8b7ea-120">如果证书中不存在本地计算机上**指纹**框中，键入或粘贴证书指纹，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8b7ea-120">If the certificate does not exist on the local computer, in the **Thumbprint** box, type or paste the certificate thumbprint, and then click **OK**.</span></span> <span data-ttu-id="8b7ea-121">证书指纹的格式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 为十六进制数字。</span><span class="sxs-lookup"><span data-stu-id="8b7ea-121">The certificate thumbprint has the format HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, where H is a hexadecimal digit.</span></span>