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
ms.openlocfilehash: c3f349dbc2eb3ffd6a1bfa38c3231461d45a8ae7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381387"
---
# <a name="invalid-client-certificate-thumbprint"></a><span data-ttu-id="e4a77-102">客户端证书指纹无效</span><span class="sxs-lookup"><span data-stu-id="e4a77-102">Invalid client certificate thumbprint</span></span>
## <a name="details"></a><span data-ttu-id="e4a77-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="e4a77-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="e4a77-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="e4a77-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="e4a77-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="e4a77-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="e4a77-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="e4a77-106">Event ID</span></span>     |                                         <span data-ttu-id="e4a77-107">0</span><span class="sxs-lookup"><span data-stu-id="e4a77-107">0</span></span>                                          |
|  <span data-ttu-id="e4a77-108">事件源</span><span class="sxs-lookup"><span data-stu-id="e4a77-108">Event Source</span></span>   |                                         <span data-ttu-id="e4a77-109">0</span><span class="sxs-lookup"><span data-stu-id="e4a77-109">0</span></span>                                          |
|    <span data-ttu-id="e4a77-110">组件</span><span class="sxs-lookup"><span data-stu-id="e4a77-110">Component</span></span>    |                                         <span data-ttu-id="e4a77-111">0</span><span class="sxs-lookup"><span data-stu-id="e4a77-111">0</span></span>                                          |
|  <span data-ttu-id="e4a77-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="e4a77-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="e4a77-113">0</span><span class="sxs-lookup"><span data-stu-id="e4a77-113">0</span></span>                                          |
|  <span data-ttu-id="e4a77-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="e4a77-114">Message Text</span></span>   |       <span data-ttu-id="e4a77-115">客户端证书指纹无效;预期的 40 个十六进制数字。</span><span class="sxs-lookup"><span data-stu-id="e4a77-115">Invalid client certificate thumbprint; expected 40 hexadecimal digits.</span></span>       |
  
## <a name="explanation"></a><span data-ttu-id="e4a77-116">解释</span><span class="sxs-lookup"><span data-stu-id="e4a77-116">Explanation</span></span>  
 <span data-ttu-id="e4a77-117">指定了无效的客户端证书指纹。</span><span class="sxs-lookup"><span data-stu-id="e4a77-117">An invalid client certificate thumbprint was specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="e4a77-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="e4a77-118">User Action</span></span>  
 <span data-ttu-id="e4a77-119">在代码中配置 WCF 发送端口，客户端证书属性的用户界面需要十六进制 40 位值。</span><span class="sxs-lookup"><span data-stu-id="e4a77-119">In the code configuring the WCF send port, the client certificate property of the user interface expects a hexadecimal 40-digit value.</span></span> <span data-ttu-id="e4a77-120">例如：798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39</span><span class="sxs-lookup"><span data-stu-id="e4a77-120">Example: 798A68E7A3E6F2CCC6929FC4AF2A15A9EED66E39</span></span>  
  
 <span data-ttu-id="e4a77-121">证书的其他信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="e4a77-121">For additional information on certificates, see the following:</span></span>  
  
-   [<span data-ttu-id="e4a77-122">安装用于 WCF 适配器的证书</span><span class="sxs-lookup"><span data-stu-id="e4a77-122">Installing Certificates for the WCF Adapters</span></span>](../core/installing-certificates-for-the-wcf-adapters.md)