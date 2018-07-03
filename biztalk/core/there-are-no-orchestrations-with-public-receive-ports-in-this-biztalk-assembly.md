---
title: 在此 BizTalk 程序集中的业务流程不具有公共接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fb901d49-ce3c-4bc6-806a-eb5964d32bb4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c062f5e23972ed841c4c9d614ad58967a07a4fe2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36978212"
---
# <a name="there-are-no-orchestrations-with-public-receive-ports-in-this-biztalk-assembly"></a><span data-ttu-id="b5ae8-102">此 BizTalk 程序集未包含具有公共接收端口的业务流程</span><span class="sxs-lookup"><span data-stu-id="b5ae8-102">There are no orchestrations with public receive ports in this BizTalk assembly</span></span>
## <a name="details"></a><span data-ttu-id="b5ae8-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b5ae8-103">Details</span></span>  
  
|                 |                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="b5ae8-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b5ae8-104">Product Name</span></span>   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| <span data-ttu-id="b5ae8-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="b5ae8-105">Product Version</span></span> |                                                          [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                           |
|    <span data-ttu-id="b5ae8-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b5ae8-106">Event ID</span></span>     |                                                                                       <span data-ttu-id="b5ae8-107">0</span><span class="sxs-lookup"><span data-stu-id="b5ae8-107">0</span></span>                                                                                       |
|  <span data-ttu-id="b5ae8-108">事件源</span><span class="sxs-lookup"><span data-stu-id="b5ae8-108">Event Source</span></span>   |                                                                                       <span data-ttu-id="b5ae8-109">0</span><span class="sxs-lookup"><span data-stu-id="b5ae8-109">0</span></span>                                                                                       |
|    <span data-ttu-id="b5ae8-110">组件</span><span class="sxs-lookup"><span data-stu-id="b5ae8-110">Component</span></span>    |                                                                                       <span data-ttu-id="b5ae8-111">0</span><span class="sxs-lookup"><span data-stu-id="b5ae8-111">0</span></span>                                                                                       |
|  <span data-ttu-id="b5ae8-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="b5ae8-112">Symbolic Name</span></span>  |                                                                                       <span data-ttu-id="b5ae8-113">0</span><span class="sxs-lookup"><span data-stu-id="b5ae8-113">0</span></span>                                                                                       |
|  <span data-ttu-id="b5ae8-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="b5ae8-114">Message Text</span></span>   | <span data-ttu-id="b5ae8-115">此 BizTalk 程序集中的业务流程不具有公共接收端口。</span><span class="sxs-lookup"><span data-stu-id="b5ae8-115">There are no orchestrations with public receive ports in this BizTalk assembly.</span></span> <span data-ttu-id="b5ae8-116">单击“上一步”，并指定包含具有公共接收端口的业务流程的 BizTalk 程序集</span><span class="sxs-lookup"><span data-stu-id="b5ae8-116">Click back and specify a BizTalk assembly containing orchestrations with public receive ports</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="b5ae8-117">解释</span><span class="sxs-lookup"><span data-stu-id="b5ae8-117">Explanation</span></span>  
 <span data-ttu-id="b5ae8-118">此错误表明选择的业务流程不具有公共端口。</span><span class="sxs-lookup"><span data-stu-id="b5ae8-118">This error indicates the orchestration selected does not have a public port.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="b5ae8-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="b5ae8-119">User Action</span></span>  
 <span data-ttu-id="b5ae8-120">使用以下过程配置公共端口。</span><span class="sxs-lookup"><span data-stu-id="b5ae8-120">Use the following procedure to configure a public port.</span></span>  
  
#### <a name="to-configure-a-public-port"></a><span data-ttu-id="b5ae8-121">配置公共端口</span><span class="sxs-lookup"><span data-stu-id="b5ae8-121">To configure a public port</span></span>  
  
1.  <span data-ttu-id="b5ae8-122">找到业务流程，并使所需接收端口成为公共端口。</span><span class="sxs-lookup"><span data-stu-id="b5ae8-122">Locate the orchestration and make the desired receive port public.</span></span>  
  
    1.  <span data-ttu-id="b5ae8-123">打开端口配置向导。</span><span class="sxs-lookup"><span data-stu-id="b5ae8-123">Open the Port Configuration wizard.</span></span>  
  
    2.  <span data-ttu-id="b5ae8-124">在中**选择端口类型**，更改**访问限制**从**内部**（默认值） 到**公有-无限制**。</span><span class="sxs-lookup"><span data-stu-id="b5ae8-124">In **Select a Port Type**, change **Access Restrictions** from **Internal** (default) to **Public-no limits**.</span></span>  
  
2.  <span data-ttu-id="b5ae8-125">重新编译程序集。</span><span class="sxs-lookup"><span data-stu-id="b5ae8-125">Recompile the assembly.</span></span>  
  
     <span data-ttu-id="b5ae8-126">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="b5ae8-126">\- OR -</span></span>  
  
     <span data-ttu-id="b5ae8-127">加载具有公共接收端口的 BizTalk 程序集。</span><span class="sxs-lookup"><span data-stu-id="b5ae8-127">Load a BizTalk assembly with public receive ports.</span></span>