---
title: 用于解密消息的证书已被吊销 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 01767cb2-b16e-4b4b-ac4d-cd79b6c8860a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7cd9404f13f737b4cb82317193344e006979d333
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22277909"
---
# <a name="the-certificate-used-to-decrypt-a-message-has-been-revoked"></a><span data-ttu-id="f6696-102">用于解密消息的证书已经被吊销</span><span class="sxs-lookup"><span data-stu-id="f6696-102">The certificate used to decrypt a message has been revoked</span></span>
## <a name="details"></a><span data-ttu-id="f6696-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f6696-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f6696-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f6696-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="f6696-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="f6696-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="f6696-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f6696-106">Event ID</span></span>|-|  
|<span data-ttu-id="f6696-107">事件源</span><span class="sxs-lookup"><span data-stu-id="f6696-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="f6696-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="f6696-108"> EDI</span></span>|  
|<span data-ttu-id="f6696-109">组件</span><span class="sxs-lookup"><span data-stu-id="f6696-109">Component</span></span>|<span data-ttu-id="f6696-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="f6696-110">AS2 Engine</span></span>|  
|<span data-ttu-id="f6696-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="f6696-111">Symbolic Name</span></span>|<span data-ttu-id="f6696-112">DecryptionCertificateHasBeenRevokedError</span><span class="sxs-lookup"><span data-stu-id="f6696-112">DecryptionCertificateHasBeenRevokedError</span></span>|  
|<span data-ttu-id="f6696-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="f6696-113">Message Text</span></span>|<span data-ttu-id="f6696-114">用于解密消息的证书已经被吊销。</span><span class="sxs-lookup"><span data-stu-id="f6696-114">The certificate used to decrypt a message has been revoked.</span></span> <span data-ttu-id="f6696-115">证书指纹： {0}</span><span class="sxs-lookup"><span data-stu-id="f6696-115">Certificate thumbprint: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f6696-116">解释</span><span class="sxs-lookup"><span data-stu-id="f6696-116">Explanation</span></span>  
 <span data-ttu-id="f6696-117">此错误/警告/信息事件表明接收管道无法处理传入的消息，因为用于解密消息的证书已被吊销。</span><span class="sxs-lookup"><span data-stu-id="f6696-117">This Error/Warning/Information event indicates that the receive pipeline could not process the incoming message because the certificate to be used to decrypt the message has been revoked.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f6696-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="f6696-118">User Action</span></span>  
 <span data-ttu-id="f6696-119">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="f6696-119">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="f6696-120">创建新的证书来替换被吊销的证书。</span><span class="sxs-lookup"><span data-stu-id="f6696-120">Create a new certificate to replace the revoked certificate.</span></span> <span data-ttu-id="f6696-121">将该证书添加到“当前用户/个人”证书存储区中，然后发送用于发送 AS2 消息的证书的公钥。</span><span class="sxs-lookup"><span data-stu-id="f6696-121">Add the certificate to the Current User/Personal certificate store, and then send the public key of the certificate to the sending of the AS2 message.</span></span>  
  
-   <span data-ttu-id="f6696-122">通过打开 BizTalk Server 管理控制台、打开为传出消息解析的参与方的“AS2 属性”对话框，单击“常规”节点，然后清除“检查证书吊销列表”属性来禁用吊销列表检查。</span><span class="sxs-lookup"><span data-stu-id="f6696-122">Disable the revocation list check by opening the BizTalk Server Administration Console, opening the AS2 Properties dialog box for the party resolved for the outgoing message, clicking the General node, and then clearing the Check Certification Revocation List property.</span></span>