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
ms.openlocfilehash: 695c2d8ef697ea3cddbdc72880a844e4ece7a8c6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292914"
---
# <a name="the-signing-certificate-has-not-been-configured-for-as2-party"></a><span data-ttu-id="ce0f8-102">尚未为 AS2 参与方配置签名证书</span><span class="sxs-lookup"><span data-stu-id="ce0f8-102">The Signing Certificate has not been configured for AS2 party</span></span>
## <a name="details"></a><span data-ttu-id="ce0f8-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="ce0f8-103">Details</span></span>  
  
|                 |                                                                                           |
|-----------------|-------------------------------------------------------------------------------------------|
|  <span data-ttu-id="ce0f8-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="ce0f8-104">Product Name</span></span>   |    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]     |
| <span data-ttu-id="ce0f8-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="ce0f8-105">Product Version</span></span> |                [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                 |
|    <span data-ttu-id="ce0f8-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ce0f8-106">Event ID</span></span>     |                                             -                                             |
|  <span data-ttu-id="ce0f8-107">事件源</span><span class="sxs-lookup"><span data-stu-id="ce0f8-107">Event Source</span></span>   |  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="ce0f8-108">EDI</span><span class="sxs-lookup"><span data-stu-id="ce0f8-108">EDI</span></span>   |
|    <span data-ttu-id="ce0f8-109">组件</span><span class="sxs-lookup"><span data-stu-id="ce0f8-109">Component</span></span>    |                                        <span data-ttu-id="ce0f8-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="ce0f8-110">AS2 Engine</span></span>                                         |
|  <span data-ttu-id="ce0f8-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="ce0f8-111">Symbolic Name</span></span>  |                               <span data-ttu-id="ce0f8-112">SigningCertNotConfiguredError</span><span class="sxs-lookup"><span data-stu-id="ce0f8-112">SigningCertNotConfiguredError</span></span>                               |
|  <span data-ttu-id="ce0f8-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="ce0f8-113">Message Text</span></span>   | <span data-ttu-id="ce0f8-114">尚未为 AS2 参与方配置签名证书。</span><span class="sxs-lookup"><span data-stu-id="ce0f8-114">The Signing Certificate has not been configured for AS2 party.</span></span>  <span data-ttu-id="ce0f8-115">AS2-从：{0} AS2-到： {1}</span><span class="sxs-lookup"><span data-stu-id="ce0f8-115">AS2-From: {0} AS2-To: {1}</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="ce0f8-116">解释</span><span class="sxs-lookup"><span data-stu-id="ce0f8-116">Explanation</span></span>  
 <span data-ttu-id="ce0f8-117">此错误/警告/信息事件表明发送管道不无法处理传出消息，因为未为该组配置签名证书。</span><span class="sxs-lookup"><span data-stu-id="ce0f8-117">This Error/Warning/Information event indicates that the send pipeline could not process the outgoing message because the signing certificate was not configured for the group.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ce0f8-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="ce0f8-118">User Action</span></span>  
 <span data-ttu-id="ce0f8-119">若要解决此错误，请通过执行以下配置签名证书：</span><span class="sxs-lookup"><span data-stu-id="ce0f8-119">To resolve this error, configure signing certificate by doing the following:</span></span>  
  
1.  <span data-ttu-id="ce0f8-120">打开 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ce0f8-120">Open the BizTalk Server Administration Console.</span></span>  
  
2.  <span data-ttu-id="ce0f8-121">将移动到组节点，然后单击证书节点。</span><span class="sxs-lookup"><span data-stu-id="ce0f8-121">Move to the Group node, and click the Certificate node.</span></span>  
  
3.  <span data-ttu-id="ce0f8-122">输入公用名称和证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="ce0f8-122">Enter the common name and thumbprint of the certificate.</span></span>