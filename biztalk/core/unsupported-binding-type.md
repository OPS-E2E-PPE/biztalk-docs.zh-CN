---
title: 不支持的绑定类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5556a7d7-f092-4f69-9561-88f51ac46cc9
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a1090157a3b39dea62a3c95cb787b91e0a33bfc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004334"
---
# <a name="unsupported-binding-type"></a><span data-ttu-id="be651-102">不支持的绑定类型</span><span class="sxs-lookup"><span data-stu-id="be651-102">Unsupported binding type</span></span>
## <a name="details"></a><span data-ttu-id="be651-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="be651-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="be651-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="be651-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="be651-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="be651-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="be651-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="be651-106">Event ID</span></span>     |                                         <span data-ttu-id="be651-107">0</span><span class="sxs-lookup"><span data-stu-id="be651-107">0</span></span>                                          |
|  <span data-ttu-id="be651-108">事件源</span><span class="sxs-lookup"><span data-stu-id="be651-108">Event Source</span></span>   |                                         <span data-ttu-id="be651-109">0</span><span class="sxs-lookup"><span data-stu-id="be651-109">0</span></span>                                          |
|    <span data-ttu-id="be651-110">组件</span><span class="sxs-lookup"><span data-stu-id="be651-110">Component</span></span>    |                                         <span data-ttu-id="be651-111">0</span><span class="sxs-lookup"><span data-stu-id="be651-111">0</span></span>                                          |
|  <span data-ttu-id="be651-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="be651-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="be651-113">0</span><span class="sxs-lookup"><span data-stu-id="be651-113">0</span></span>                                          |
|  <span data-ttu-id="be651-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="be651-114">Message Text</span></span>   |                              <span data-ttu-id="be651-115">不支持的绑定类型</span><span class="sxs-lookup"><span data-stu-id="be651-115">Unsupported binding type</span></span>                              |
  
## <a name="explanation"></a><span data-ttu-id="be651-116">解释</span><span class="sxs-lookup"><span data-stu-id="be651-116">Explanation</span></span>  
 <span data-ttu-id="be651-117">已经选择 MsmqIntegration 绑定，但 WCF 适配器不支持该绑定。</span><span class="sxs-lookup"><span data-stu-id="be651-117">The MsmqIntegration binding was chosen, but is not supported by the WCF adapter.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="be651-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="be651-118">User Action</span></span>  
 <span data-ttu-id="be651-119">使用 WCF-NetMsmq 适配器。</span><span class="sxs-lookup"><span data-stu-id="be651-119">Use the WCF-NetMsmq adapter.</span></span> <span data-ttu-id="be651-120">如果需要交换本地 MSMQ 消息，则使用 BizTalk MSMQ 适配器。</span><span class="sxs-lookup"><span data-stu-id="be651-120">If native MSMQ messages need to be exchanged, use the BizTalk MSMQ adapter.</span></span>  
  
 <span data-ttu-id="be651-121">有关配置适配器的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="be651-121">For further information on configuring adapters, see the following resource:</span></span>  
  
-   [<span data-ttu-id="be651-122">配置 WCF-NetMsmq 适配器</span><span class="sxs-lookup"><span data-stu-id="be651-122">Configuring the WCF-NetMsmq Adapter</span></span>](../core/configuring-the-wcf-netmsmq-adapter.md)