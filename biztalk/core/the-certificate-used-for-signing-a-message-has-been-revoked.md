---
title: 用于对邮件签名的证书已被吊销 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f822235a-8ad8-4b63-94de-9b7f9361a071
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8527f89d03d3250a7685380fcabf484254fbbf86
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278229"
---
# <a name="the-certificate-used-for-signing-a-message-has-been-revoked"></a><span data-ttu-id="415a1-102">用于对消息进行签名的证书已经被吊销</span><span class="sxs-lookup"><span data-stu-id="415a1-102">The certificate used for signing a message has been revoked</span></span>
## <a name="details"></a><span data-ttu-id="415a1-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="415a1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="415a1-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="415a1-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="415a1-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="415a1-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="415a1-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="415a1-106">Event ID</span></span>|-|  
|<span data-ttu-id="415a1-107">事件源</span><span class="sxs-lookup"><span data-stu-id="415a1-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="415a1-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="415a1-108"> EDI</span></span>|  
|<span data-ttu-id="415a1-109">组件</span><span class="sxs-lookup"><span data-stu-id="415a1-109">Component</span></span>|<span data-ttu-id="415a1-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="415a1-110">AS2 Engine</span></span>|  
|<span data-ttu-id="415a1-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="415a1-111">Symbolic Name</span></span>|<span data-ttu-id="415a1-112">SigningCertificateHasBeenRevokedError</span><span class="sxs-lookup"><span data-stu-id="415a1-112">SigningCertificateHasBeenRevokedError</span></span>|  
|<span data-ttu-id="415a1-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="415a1-113">Message Text</span></span>|<span data-ttu-id="415a1-114">用于对消息进行签名的证书已经被吊销。</span><span class="sxs-lookup"><span data-stu-id="415a1-114">The certificate used for signing a message has been revoked.</span></span> <span data-ttu-id="415a1-115">证书指纹： {0}</span><span class="sxs-lookup"><span data-stu-id="415a1-115">Certificate thumbprint: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="415a1-116">解释</span><span class="sxs-lookup"><span data-stu-id="415a1-116">Explanation</span></span>  
 <span data-ttu-id="415a1-117">此错误/警告/信息事件表明发送管道无法处理传出的消息，因为标识为签名证书的证书已被吊销。</span><span class="sxs-lookup"><span data-stu-id="415a1-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing message because the certificate identified as the signing certificate has been revoked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="415a1-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="415a1-118">User Action</span></span>  
 <span data-ttu-id="415a1-119">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="415a1-119">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="415a1-120">创建一个新的证书来替换已吊销的证书。</span><span class="sxs-lookup"><span data-stu-id="415a1-120">Create a new certificate to replaced the revoked certificate.</span></span> <span data-ttu-id="415a1-121">将证书添加到“当前用户”证书存储区中，在“组属性”对话框的“证书”页中将其标识为签名证书，然后将该证书的公钥发送给 AS2 消息的收件人。</span><span class="sxs-lookup"><span data-stu-id="415a1-121">Add the certificate to the Current User certificate store, identify it as the signing certificate in the Certificate page of the Group Properties dialog box, and then send the public key of the certificate to the recipient of the AS2 message.</span></span>  
  
-   <span data-ttu-id="415a1-122">通过打开 BizTalk Server 管理控制台、打开为传出消息解析的参与方的“AS2 属性”对话框，单击“常规”节点，然后清除“检查证书吊销列表”属性来禁用吊销列表检查。</span><span class="sxs-lookup"><span data-stu-id="415a1-122">Disable the revocation list check by opening the BizTalk Server Administration Console, opening the AS2 Properties dialog box for the party resolved for the outgoing message, clicking the General node, and then clearing the Check Certification Revocation List property.</span></span>