---
title: 无效的客户端证书指纹 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f18fa0a2-b0d9-4190-aa96-12ab7007edd1
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74551ac825f9e517bec1d07edc7f288db732b348
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37018879"
---
# <a name="invalid-client-certificate-thumbprint"></a><span data-ttu-id="0d292-102">客户端证书指纹无效</span><span class="sxs-lookup"><span data-stu-id="0d292-102">Invalid client certificate thumbprint</span></span>
## <a name="details"></a><span data-ttu-id="0d292-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="0d292-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="0d292-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="0d292-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="0d292-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="0d292-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="0d292-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0d292-106">Event ID</span></span>     |                                         <span data-ttu-id="0d292-107">0</span><span class="sxs-lookup"><span data-stu-id="0d292-107">0</span></span>                                          |
|  <span data-ttu-id="0d292-108">事件源</span><span class="sxs-lookup"><span data-stu-id="0d292-108">Event Source</span></span>   |                                         <span data-ttu-id="0d292-109">0</span><span class="sxs-lookup"><span data-stu-id="0d292-109">0</span></span>                                          |
|    <span data-ttu-id="0d292-110">组件</span><span class="sxs-lookup"><span data-stu-id="0d292-110">Component</span></span>    |                                         <span data-ttu-id="0d292-111">0</span><span class="sxs-lookup"><span data-stu-id="0d292-111">0</span></span>                                          |
|  <span data-ttu-id="0d292-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="0d292-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="0d292-113">0</span><span class="sxs-lookup"><span data-stu-id="0d292-113">0</span></span>                                          |
|  <span data-ttu-id="0d292-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="0d292-114">Message Text</span></span>   |       <span data-ttu-id="0d292-115">客户端证书指纹无效；应为十六进制的 40 位数字。</span><span class="sxs-lookup"><span data-stu-id="0d292-115">Invalid client certificate thumbprint; expected 40 hexadecimal digits.</span></span>       |
  
## <a name="explanation"></a><span data-ttu-id="0d292-116">解释</span><span class="sxs-lookup"><span data-stu-id="0d292-116">Explanation</span></span>  
 <span data-ttu-id="0d292-117">指定的客户端证书指纹无效。</span><span class="sxs-lookup"><span data-stu-id="0d292-117">An invalid client certificate thumbprint was specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0d292-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="0d292-118">User Action</span></span>  
 <span data-ttu-id="0d292-119">在用于配置 WCF 发送端口的代码中，用户界面的客户端证书属性应为十六进制的 40 位值。</span><span class="sxs-lookup"><span data-stu-id="0d292-119">In the code configuring the WCF send port, the client certificate property of the user interface expects a hexadecimal 40-digit value.</span></span> <span data-ttu-id="0d292-120">示例： 798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39</span><span class="sxs-lookup"><span data-stu-id="0d292-120">Example: 798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39</span></span>  
  
 <span data-ttu-id="0d292-121">有关证书的其他信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="0d292-121">For additional information on certificates, see the following:</span></span>  
  
-   [<span data-ttu-id="0d292-122">安装用于 WCF 适配器的证书</span><span class="sxs-lookup"><span data-stu-id="0d292-122">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)