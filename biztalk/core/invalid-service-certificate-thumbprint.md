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
ms.openlocfilehash: 5dcd37c3f3f2d56a9bdc2c576fee344a0eef7df4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005143"
---
# <a name="invalid-service-certificate-thumbprint"></a><span data-ttu-id="e89c7-102">服务证书指纹无效</span><span class="sxs-lookup"><span data-stu-id="e89c7-102">Invalid service certificate thumbprint</span></span>
## <a name="details"></a><span data-ttu-id="e89c7-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e89c7-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="e89c7-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e89c7-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="e89c7-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="e89c7-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="e89c7-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e89c7-106">Event ID</span></span>     |                                         <span data-ttu-id="e89c7-107">0</span><span class="sxs-lookup"><span data-stu-id="e89c7-107">0</span></span>                                          |
|  <span data-ttu-id="e89c7-108">事件源</span><span class="sxs-lookup"><span data-stu-id="e89c7-108">Event Source</span></span>   |                                         <span data-ttu-id="e89c7-109">0</span><span class="sxs-lookup"><span data-stu-id="e89c7-109">0</span></span>                                          |
|    <span data-ttu-id="e89c7-110">组件</span><span class="sxs-lookup"><span data-stu-id="e89c7-110">Component</span></span>    |                                         <span data-ttu-id="e89c7-111">0</span><span class="sxs-lookup"><span data-stu-id="e89c7-111">0</span></span>                                          |
|  <span data-ttu-id="e89c7-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="e89c7-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="e89c7-113">0</span><span class="sxs-lookup"><span data-stu-id="e89c7-113">0</span></span>                                          |
|  <span data-ttu-id="e89c7-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="e89c7-114">Message Text</span></span>   |       <span data-ttu-id="e89c7-115">服务证书指纹无效；应为十六进制的 40 位数字</span><span class="sxs-lookup"><span data-stu-id="e89c7-115">Invalid service certificate thumbprint; expected 40 hexadecimal digits</span></span>       |
  
## <a name="explanation"></a><span data-ttu-id="e89c7-116">解释</span><span class="sxs-lookup"><span data-stu-id="e89c7-116">Explanation</span></span>  
 <span data-ttu-id="e89c7-117">指定的服务证书指纹无效。</span><span class="sxs-lookup"><span data-stu-id="e89c7-117">An invalid service certificate thumbprint was specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e89c7-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="e89c7-118">User Action</span></span>  
 <span data-ttu-id="e89c7-119">在用于配置 WCF 端口的代码中，用户界面的服务证书属性应为十六进制的 40 位数字值。</span><span class="sxs-lookup"><span data-stu-id="e89c7-119">In the code configuring the WCF port, the service certificate property of the user interface expects a hexadecimal 40-digit value.</span></span> <span data-ttu-id="e89c7-120">示例： 798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39</span><span class="sxs-lookup"><span data-stu-id="e89c7-120">Example: 798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39</span></span>  
  
 <span data-ttu-id="e89c7-121">有关证书的其他信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="e89c7-121">For additional information on certificates, see the following resource:</span></span>  
  
-   [<span data-ttu-id="e89c7-122">安装用于 WCF 适配器的证书</span><span class="sxs-lookup"><span data-stu-id="e89c7-122">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)