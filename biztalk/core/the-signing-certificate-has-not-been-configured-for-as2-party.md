---
title: 尚未为 AS2 参与方配置签名证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 82928a39-3acf-447b-a0e8-f7c25b6f38dc
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4d26323670f0229377b304e5f51671de8ef10021
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967542"
---
# <a name="the-signing-certificate-has-not-been-configured-for-as2-party"></a><span data-ttu-id="76123-102">尚未为 AS2 参与方配置签名证书</span><span class="sxs-lookup"><span data-stu-id="76123-102">The Signing Certificate has not been configured for AS2 party</span></span>
## <a name="details"></a><span data-ttu-id="76123-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="76123-103">Details</span></span>  
  
|                 |                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------|
|  <span data-ttu-id="76123-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="76123-104">Product Name</span></span>   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]     |
| <span data-ttu-id="76123-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="76123-105">Product Version</span></span> |                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                 |
|    <span data-ttu-id="76123-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="76123-106">Event ID</span></span>     |                                             -                                             |
|  <span data-ttu-id="76123-107">事件源</span><span class="sxs-lookup"><span data-stu-id="76123-107">Event Source</span></span>   |  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="76123-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="76123-108"> EDI</span></span>   |
|    <span data-ttu-id="76123-109">组件</span><span class="sxs-lookup"><span data-stu-id="76123-109">Component</span></span>    |                                        <span data-ttu-id="76123-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="76123-110">AS2 Engine</span></span>                                         |
|  <span data-ttu-id="76123-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="76123-111">Symbolic Name</span></span>  |                               <span data-ttu-id="76123-112">SigningCertNotConfiguredError</span><span class="sxs-lookup"><span data-stu-id="76123-112">SigningCertNotConfiguredError</span></span>                               |
|  <span data-ttu-id="76123-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="76123-113">Message Text</span></span>   | <span data-ttu-id="76123-114">尚未为 AS2 参与方配置签名证书。</span><span class="sxs-lookup"><span data-stu-id="76123-114">The Signing Certificate has not been configured for AS2 party.</span></span>  <span data-ttu-id="76123-115">AS2-从： {0} AS2-到： {1}</span><span class="sxs-lookup"><span data-stu-id="76123-115">AS2-From: {0} AS2-To: {1}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="76123-116">解释</span><span class="sxs-lookup"><span data-stu-id="76123-116">Explanation</span></span>  
 <span data-ttu-id="76123-117">此错误/警告/信息事件表明发送管道无法处理传出的消息，因为没有为该组配置签名证书。</span><span class="sxs-lookup"><span data-stu-id="76123-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing message because the signing certificate was not configured for the group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="76123-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="76123-118">User Action</span></span>  
 <span data-ttu-id="76123-119">若要解决此错误，请通过执行以下操作配置签名证书：</span><span class="sxs-lookup"><span data-stu-id="76123-119">To resolve this error, configure signing certificate by doing the following:</span></span>  
  
1.  <span data-ttu-id="76123-120">打开 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="76123-120">Open the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="76123-121">移动到“组”节点，然后单击“证书”节点。</span><span class="sxs-lookup"><span data-stu-id="76123-121">Move to the Group node, and click the Certificate node.</span></span>  
  
3.  <span data-ttu-id="76123-122">输入证书的通用名称和指纹。</span><span class="sxs-lookup"><span data-stu-id="76123-122">Enter the common name and thumbprint of the certificate.</span></span>