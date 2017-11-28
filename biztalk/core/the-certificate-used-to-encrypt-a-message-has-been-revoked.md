---
title: "使用对消息进行加密的证书已被吊销 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76c90690-002a-43bc-85f2-8aa5e7511ffa
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4fbe34dcd2906d79a8d80ebdd00c3d9f293e6559
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="the-certificate-used-to-encrypt-a-message-has-been-revoked"></a><span data-ttu-id="449bc-102">用于加密消息的证书已经被吊销</span><span class="sxs-lookup"><span data-stu-id="449bc-102">The certificate used to encrypt a message has been revoked</span></span>
## <a name="details"></a><span data-ttu-id="449bc-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="449bc-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="449bc-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="449bc-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="449bc-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="449bc-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="449bc-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="449bc-106">Event ID</span></span>|-|  
|<span data-ttu-id="449bc-107">事件源</span><span class="sxs-lookup"><span data-stu-id="449bc-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="449bc-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="449bc-108"> EDI</span></span>|  
|<span data-ttu-id="449bc-109">组件</span><span class="sxs-lookup"><span data-stu-id="449bc-109">Component</span></span>|<span data-ttu-id="449bc-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="449bc-110">AS2 Engine</span></span>|  
|<span data-ttu-id="449bc-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="449bc-111">Symbolic Name</span></span>|<span data-ttu-id="449bc-112">EncryptionCertificateHasBeenRevokedError</span><span class="sxs-lookup"><span data-stu-id="449bc-112">EncryptionCertificateHasBeenRevokedError</span></span>|  
|<span data-ttu-id="449bc-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="449bc-113">Message Text</span></span>|<span data-ttu-id="449bc-114">用于加密消息的证书已经被吊销。</span><span class="sxs-lookup"><span data-stu-id="449bc-114">The certificate used to encrypt a message has been revoked.</span></span> <span data-ttu-id="449bc-115">证书指纹： {0}</span><span class="sxs-lookup"><span data-stu-id="449bc-115">Certificate thumbprint: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="449bc-116">解释</span><span class="sxs-lookup"><span data-stu-id="449bc-116">Explanation</span></span>  
 <span data-ttu-id="449bc-117">此错误/警告/信息事件表明发送管道无法处理传出的消息，因为标识为加密证书的证书已被吊销。</span><span class="sxs-lookup"><span data-stu-id="449bc-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing message because the certificate identified as the encryption certificate has been revoked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="449bc-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="449bc-118">User Action</span></span>  
 <span data-ttu-id="449bc-119">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="449bc-119">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="449bc-120">让消息的接收方创建一个新证书并将公钥发送给您。</span><span class="sxs-lookup"><span data-stu-id="449bc-120">Have the receiver of the message create a new certificate and send the public key to you.</span></span> <span data-ttu-id="449bc-121">将证书添加到“本地计算机\其他人”证书存储区中，然后在“发送端口属性”对话框的“证书”页中将该证书标识为加密证书。</span><span class="sxs-lookup"><span data-stu-id="449bc-121">Add the certificate to the Local computer\Other People certificate store, and then identify the certificate as the encryption certificate in the Certificate page of the Send Port Properties dialog box.</span></span>  
  
-   <span data-ttu-id="449bc-122">通过打开 BizTalk Server 管理控制台、打开为传出消息解析的参与方的“AS2 属性”对话框，单击“常规”节点，然后清除“检查证书吊销列表”属性来禁用吊销列表检查。</span><span class="sxs-lookup"><span data-stu-id="449bc-122">Disable the revocation list check by opening the BizTalk Server Administration Console, opening the AS2 Properties dialog box for the party resolved for the outgoing message, clicking the General node, and then clearing the Check Certification Revocation List property.</span></span>