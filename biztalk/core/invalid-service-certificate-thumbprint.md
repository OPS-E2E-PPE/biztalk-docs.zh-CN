---
title: 服务证书指纹无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 22e7d74e-40ec-4187-9246-bc8da2a9ce86
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 42d47f05542fa69279e65c3c71566f9f60787241
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330421"
---
# <a name="invalid-service-certificate-thumbprint"></a><span data-ttu-id="1cdf4-102">服务证书指纹无效</span><span class="sxs-lookup"><span data-stu-id="1cdf4-102">Invalid service certificate thumbprint</span></span>
## <a name="details"></a><span data-ttu-id="1cdf4-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="1cdf4-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="1cdf4-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="1cdf4-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="1cdf4-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="1cdf4-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="1cdf4-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="1cdf4-106">Event ID</span></span>     |                                         <span data-ttu-id="1cdf4-107">0</span><span class="sxs-lookup"><span data-stu-id="1cdf4-107">0</span></span>                                          |
|  <span data-ttu-id="1cdf4-108">事件源</span><span class="sxs-lookup"><span data-stu-id="1cdf4-108">Event Source</span></span>   |                                         <span data-ttu-id="1cdf4-109">0</span><span class="sxs-lookup"><span data-stu-id="1cdf4-109">0</span></span>                                          |
|    <span data-ttu-id="1cdf4-110">组件</span><span class="sxs-lookup"><span data-stu-id="1cdf4-110">Component</span></span>    |                                         <span data-ttu-id="1cdf4-111">0</span><span class="sxs-lookup"><span data-stu-id="1cdf4-111">0</span></span>                                          |
|  <span data-ttu-id="1cdf4-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="1cdf4-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="1cdf4-113">0</span><span class="sxs-lookup"><span data-stu-id="1cdf4-113">0</span></span>                                          |
|  <span data-ttu-id="1cdf4-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="1cdf4-114">Message Text</span></span>   |       <span data-ttu-id="1cdf4-115">服务证书指纹无效;预期的 40 个十六进制数字</span><span class="sxs-lookup"><span data-stu-id="1cdf4-115">Invalid service certificate thumbprint; expected 40 hexadecimal digits</span></span>       |
  
## <a name="explanation"></a><span data-ttu-id="1cdf4-116">解释</span><span class="sxs-lookup"><span data-stu-id="1cdf4-116">Explanation</span></span>  
 <span data-ttu-id="1cdf4-117">指定了无效的服务证书指纹。</span><span class="sxs-lookup"><span data-stu-id="1cdf4-117">An invalid service certificate thumbprint was specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1cdf4-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="1cdf4-118">User Action</span></span>  
 <span data-ttu-id="1cdf4-119">在代码中配置 WCF 端口，用户界面的服务证书属性应十六进制的 40 位值。</span><span class="sxs-lookup"><span data-stu-id="1cdf4-119">In the code configuring the WCF port, the service certificate property of the user interface expects a hexadecimal 40-digit value.</span></span> <span data-ttu-id="1cdf4-120">例如：798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39</span><span class="sxs-lookup"><span data-stu-id="1cdf4-120">Example: 798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39</span></span>  
  
 <span data-ttu-id="1cdf4-121">有关证书的其他信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="1cdf4-121">For additional information on certificates, see the following resource:</span></span>  
  
-   [<span data-ttu-id="1cdf4-122">安装用于 WCF 适配器的证书</span><span class="sxs-lookup"><span data-stu-id="1cdf4-122">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)