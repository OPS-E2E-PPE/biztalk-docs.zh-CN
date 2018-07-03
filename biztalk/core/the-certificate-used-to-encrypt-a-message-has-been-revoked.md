---
title: 用于对消息进行加密的证书已被吊销 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76c90690-002a-43bc-85f2-8aa5e7511ffa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4476249160f71e20012ff92f749042775132d5e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36971430"
---
# <a name="the-certificate-used-to-encrypt-a-message-has-been-revoked"></a><span data-ttu-id="50a67-102">用于加密消息的证书已经被吊销</span><span class="sxs-lookup"><span data-stu-id="50a67-102">The certificate used to encrypt a message has been revoked</span></span>
## <a name="details"></a><span data-ttu-id="50a67-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="50a67-103">Details</span></span>  
  
|                 |                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------|
|  <span data-ttu-id="50a67-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="50a67-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]    |
| <span data-ttu-id="50a67-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="50a67-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                |
|    <span data-ttu-id="50a67-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="50a67-106">Event ID</span></span>     |                                            -                                            |
|  <span data-ttu-id="50a67-107">事件源</span><span class="sxs-lookup"><span data-stu-id="50a67-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="50a67-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="50a67-108"> EDI</span></span>  |
|    <span data-ttu-id="50a67-109">组件</span><span class="sxs-lookup"><span data-stu-id="50a67-109">Component</span></span>    |                                       <span data-ttu-id="50a67-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="50a67-110">AS2 Engine</span></span>                                        |
|  <span data-ttu-id="50a67-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="50a67-111">Symbolic Name</span></span>  |                        <span data-ttu-id="50a67-112">EncryptionCertificateHasBeenRevokedError</span><span class="sxs-lookup"><span data-stu-id="50a67-112">EncryptionCertificateHasBeenRevokedError</span></span>                         |
|  <span data-ttu-id="50a67-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="50a67-113">Message Text</span></span>   | <span data-ttu-id="50a67-114">用于加密消息的证书已经被吊销。</span><span class="sxs-lookup"><span data-stu-id="50a67-114">The certificate used to encrypt a message has been revoked.</span></span> <span data-ttu-id="50a67-115">证书指纹： {0}</span><span class="sxs-lookup"><span data-stu-id="50a67-115">Certificate thumbprint: {0}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="50a67-116">解释</span><span class="sxs-lookup"><span data-stu-id="50a67-116">Explanation</span></span>  
 <span data-ttu-id="50a67-117">此错误/警告/信息事件表明发送管道无法处理传出的消息，因为标识为加密证书的证书已被吊销。</span><span class="sxs-lookup"><span data-stu-id="50a67-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing message because the certificate identified as the encryption certificate has been revoked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="50a67-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="50a67-118">User Action</span></span>  
 <span data-ttu-id="50a67-119">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="50a67-119">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="50a67-120">让消息的接收方创建一个新证书并将公钥发送给您。</span><span class="sxs-lookup"><span data-stu-id="50a67-120">Have the receiver of the message create a new certificate and send the public key to you.</span></span> <span data-ttu-id="50a67-121">将证书添加到“本地计算机\其他人”证书存储区中，然后在“发送端口属性”对话框的“证书”页中将该证书标识为加密证书。</span><span class="sxs-lookup"><span data-stu-id="50a67-121">Add the certificate to the Local computer\Other People certificate store, and then identify the certificate as the encryption certificate in the Certificate page of the Send Port Properties dialog box.</span></span>  
  
-   <span data-ttu-id="50a67-122">通过打开 BizTalk Server 管理控制台、打开为传出消息解析的参与方的“AS2 属性”对话框，单击“常规”节点，然后清除“检查证书吊销列表”属性来禁用吊销列表检查。</span><span class="sxs-lookup"><span data-stu-id="50a67-122">Disable the revocation list check by opening the BizTalk Server Administration Console, opening the AS2 Properties dialog box for the party resolved for the outgoing message, clicking the General node, and then clearing the Check Certification Revocation List property.</span></span>