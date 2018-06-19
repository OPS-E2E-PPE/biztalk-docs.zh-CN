---
title: 用于对邮件签名的证书不能位于在本地证书存储区中 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2ff3c7a2-954c-4c62-a7b2-06f7a38d61b3
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d94049a0ecca4e7aec89c5163231c0b9bf4c9e3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239957"
---
# <a name="the-certificate-used-for-signing-a-message-cannot-be-located-in-the-local-certificate-store"></a><span data-ttu-id="d8ce9-102">无法在本地证书存储中定位用于对消息签名的证书</span><span class="sxs-lookup"><span data-stu-id="d8ce9-102">The certificate used for signing a message cannot be located in the local certificate store</span></span>
## <a name="details"></a><span data-ttu-id="d8ce9-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d8ce9-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d8ce9-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d8ce9-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d8ce9-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="d8ce9-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="d8ce9-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d8ce9-106">Event ID</span></span>|-|  
|<span data-ttu-id="d8ce9-107">事件源</span><span class="sxs-lookup"><span data-stu-id="d8ce9-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="d8ce9-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="d8ce9-108"> EDI</span></span>|  
|<span data-ttu-id="d8ce9-109">组件</span><span class="sxs-lookup"><span data-stu-id="d8ce9-109">Component</span></span>|<span data-ttu-id="d8ce9-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="d8ce9-110">AS2 Engine</span></span>|  
|<span data-ttu-id="d8ce9-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="d8ce9-111">Symbolic Name</span></span>|<span data-ttu-id="d8ce9-112">CertificateMissingError</span><span class="sxs-lookup"><span data-stu-id="d8ce9-112">CertificateMissingError</span></span>|  
|<span data-ttu-id="d8ce9-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="d8ce9-113">Message Text</span></span>|<span data-ttu-id="d8ce9-114">无法在本地证书存储中定位用于对消息签名的证书。</span><span class="sxs-lookup"><span data-stu-id="d8ce9-114">The certificate used for signing a message cannot be located in the local certificate store.</span></span> <span data-ttu-id="d8ce9-115">证书指纹： {0}</span><span class="sxs-lookup"><span data-stu-id="d8ce9-115">Certificate thumbprint: {0}</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d8ce9-116">解释</span><span class="sxs-lookup"><span data-stu-id="d8ce9-116">Explanation</span></span>  
 <span data-ttu-id="d8ce9-117">此错误/警告/信息事件表明发送管道无法处理传出的消息，因为标识为签名证书的证书不在所需的证书存储区中。</span><span class="sxs-lookup"><span data-stu-id="d8ce9-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing message because the certificate identified as the signing certificate was not in the required certificate store.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d8ce9-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="d8ce9-118">User Action</span></span>  
 <span data-ttu-id="d8ce9-119">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d8ce9-119">To resolve this error, do the following:</span></span>  
  
1.  <span data-ttu-id="d8ce9-120">通过打开 BizTalk Server 管理控制台，右键单击“BizTalk 组”，然后单击“证书”节点来标识签名证书。</span><span class="sxs-lookup"><span data-stu-id="d8ce9-120">Identify the signing certificate by opening the BizTalk Server Administration Console, right-clicking the BizTalk Group, and then clicking the Certificate node.</span></span>  
  
2.  <span data-ttu-id="d8ce9-121">打开 MMC，添加“我的用户帐户”的管理单元，然后打开“证书”、“个人”和“证书”节点。</span><span class="sxs-lookup"><span data-stu-id="d8ce9-121">Open MMC, add the snap-in for the My user account, and then open the Certificates, Personal, and Certificates node.</span></span>  
  
3.  <span data-ttu-id="d8ce9-122">通过查找在错误消息文本中标识的指纹，确保“当前用户”证书存储区包含该签名证书的私钥。</span><span class="sxs-lookup"><span data-stu-id="d8ce9-122">Make sure that the Current User certificate store contains the private key for that signing certificate by looking for the thumbprint identified in the error message text.</span></span>