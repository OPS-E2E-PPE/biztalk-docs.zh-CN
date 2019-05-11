---
title: 不能在本地证书存储中定位用于对消息进行签名的证书 |Microsoft Docs
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
ms.openlocfilehash: f452ff362a11a824f749fc1a9c87b0905340c467
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65348965"
---
# <a name="the-certificate-used-for-signing-a-message-cannot-be-located-in-the-local-certificate-store"></a><span data-ttu-id="dc127-102">不能在本地证书存储中定位用于对消息进行签名的证书</span><span class="sxs-lookup"><span data-stu-id="dc127-102">The certificate used for signing a message cannot be located in the local certificate store</span></span>
## <a name="details"></a><span data-ttu-id="dc127-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="dc127-103">Details</span></span>  
  
|                 |                                                                                                                          |
|-----------------|--------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="dc127-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="dc127-104">Product Name</span></span>   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                    |
| <span data-ttu-id="dc127-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="dc127-105">Product Version</span></span> |                                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                |
|    <span data-ttu-id="dc127-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="dc127-106">Event ID</span></span>     |                                                            -                                                             |
|  <span data-ttu-id="dc127-107">事件源</span><span class="sxs-lookup"><span data-stu-id="dc127-107">Event Source</span></span>   |                  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="dc127-108">EDI</span><span class="sxs-lookup"><span data-stu-id="dc127-108">EDI</span></span>                  |
|    <span data-ttu-id="dc127-109">组件</span><span class="sxs-lookup"><span data-stu-id="dc127-109">Component</span></span>    |                                                        <span data-ttu-id="dc127-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="dc127-110">AS2 Engine</span></span>                                                        |
|  <span data-ttu-id="dc127-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="dc127-111">Symbolic Name</span></span>  |                                                 <span data-ttu-id="dc127-112">CertificateMissingError</span><span class="sxs-lookup"><span data-stu-id="dc127-112">CertificateMissingError</span></span>                                                  |
|  <span data-ttu-id="dc127-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="dc127-113">Message Text</span></span>   | <span data-ttu-id="dc127-114">不能本地证书存储中定位用于对消息进行签名的证书。</span><span class="sxs-lookup"><span data-stu-id="dc127-114">The certificate used for signing a message cannot be located in the local certificate store.</span></span> <span data-ttu-id="dc127-115">证书指纹： {0}</span><span class="sxs-lookup"><span data-stu-id="dc127-115">Certificate thumbprint: {0}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="dc127-116">解释</span><span class="sxs-lookup"><span data-stu-id="dc127-116">Explanation</span></span>  
 <span data-ttu-id="dc127-117">此错误/警告/信息事件表明发送管道不无法处理传出消息，因为标识为签名证书的证书不在所需的证书存储区中。</span><span class="sxs-lookup"><span data-stu-id="dc127-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing message because the certificate identified as the signing certificate was not in the required certificate store.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dc127-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="dc127-118">User Action</span></span>  
 <span data-ttu-id="dc127-119">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="dc127-119">To resolve this error, do the following:</span></span>  
  
1.  <span data-ttu-id="dc127-120">通过打开 BizTalk Server 管理控制台中，右键单击 BizTalk 组，然后单击证书节点标识签名证书。</span><span class="sxs-lookup"><span data-stu-id="dc127-120">Identify the signing certificate by opening the BizTalk Server Administration Console, right-clicking the BizTalk Group, and then clicking the Certificate node.</span></span>  
  
2.  <span data-ttu-id="dc127-121">打开 MMC，添加管理单元为我的用户帐户，然后打开证书、 个人和证书节点。</span><span class="sxs-lookup"><span data-stu-id="dc127-121">Open MMC, add the snap-in for the My user account, and then open the Certificates, Personal, and Certificates node.</span></span>  
  
3.  <span data-ttu-id="dc127-122">请确保当前用户证书存储区通过查看错误消息文本中标识的指纹包含该签名证书的私钥。</span><span class="sxs-lookup"><span data-stu-id="dc127-122">Make sure that the Current User certificate store contains the private key for that signing certificate by looking for the thumbprint identified in the error message text.</span></span>