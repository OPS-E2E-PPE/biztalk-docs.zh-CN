---
title: 无效的客户端证书指纹 |Microsoft 文档
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
ms.openlocfilehash: 84401d28261b13c6f49a063f34e29054a4aba108
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257405"
---
# <a name="invalid-client-certificate-thumbprint"></a><span data-ttu-id="795e6-102">客户端证书指纹无效</span><span class="sxs-lookup"><span data-stu-id="795e6-102">Invalid client certificate thumbprint</span></span>
## <a name="details"></a><span data-ttu-id="795e6-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="795e6-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="795e6-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="795e6-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="795e6-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="795e6-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="795e6-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="795e6-106">Event ID</span></span>|<span data-ttu-id="795e6-107">0</span><span class="sxs-lookup"><span data-stu-id="795e6-107">0</span></span>|  
|<span data-ttu-id="795e6-108">事件源</span><span class="sxs-lookup"><span data-stu-id="795e6-108">Event Source</span></span>|<span data-ttu-id="795e6-109">0</span><span class="sxs-lookup"><span data-stu-id="795e6-109">0</span></span>|  
|<span data-ttu-id="795e6-110">组件</span><span class="sxs-lookup"><span data-stu-id="795e6-110">Component</span></span>|<span data-ttu-id="795e6-111">0</span><span class="sxs-lookup"><span data-stu-id="795e6-111">0</span></span>|  
|<span data-ttu-id="795e6-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="795e6-112">Symbolic Name</span></span>|<span data-ttu-id="795e6-113">0</span><span class="sxs-lookup"><span data-stu-id="795e6-113">0</span></span>|  
|<span data-ttu-id="795e6-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="795e6-114">Message Text</span></span>|<span data-ttu-id="795e6-115">客户端证书指纹无效；应为十六进制的 40 位数字。</span><span class="sxs-lookup"><span data-stu-id="795e6-115">Invalid client certificate thumbprint; expected 40 hexadecimal digits.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="795e6-116">解释</span><span class="sxs-lookup"><span data-stu-id="795e6-116">Explanation</span></span>  
 <span data-ttu-id="795e6-117">指定的客户端证书指纹无效。</span><span class="sxs-lookup"><span data-stu-id="795e6-117">An invalid client certificate thumbprint was specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="795e6-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="795e6-118">User Action</span></span>  
 <span data-ttu-id="795e6-119">在用于配置 WCF 发送端口的代码中，用户界面的客户端证书属性应为十六进制的 40 位值。</span><span class="sxs-lookup"><span data-stu-id="795e6-119">In the code configuring the WCF send port, the client certificate property of the user interface expects a hexadecimal 40-digit value.</span></span> <span data-ttu-id="795e6-120">示例： 798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39</span><span class="sxs-lookup"><span data-stu-id="795e6-120">Example: 798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39</span></span>  
  
 <span data-ttu-id="795e6-121">有关证书的其他信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="795e6-121">For additional information on certificates, see the following:</span></span>  
  
-   [<span data-ttu-id="795e6-122">将证书安装适用于这些 WCF 适配器</span><span class="sxs-lookup"><span data-stu-id="795e6-122">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)