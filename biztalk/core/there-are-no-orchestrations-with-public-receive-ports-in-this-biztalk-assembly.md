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
ms.openlocfilehash: 4f4693321e02d0da6d8cec9b5ae1542fd62af6c5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400542"
---
# <a name="there-are-no-orchestrations-with-public-receive-ports-in-this-biztalk-assembly"></a><span data-ttu-id="f20d5-102">在此 BizTalk 程序集中的业务流程不具有公共接收端口</span><span class="sxs-lookup"><span data-stu-id="f20d5-102">There are no orchestrations with public receive ports in this BizTalk assembly</span></span>
## <a name="details"></a><span data-ttu-id="f20d5-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f20d5-103">Details</span></span>  
  
|                 |                                                                                                                                                                               |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f20d5-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f20d5-104">Product Name</span></span>   |                                              [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                               |
| <span data-ttu-id="f20d5-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="f20d5-105">Product Version</span></span> |                                                          [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                                           |
|    <span data-ttu-id="f20d5-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f20d5-106">Event ID</span></span>     |                                                                                       <span data-ttu-id="f20d5-107">0</span><span class="sxs-lookup"><span data-stu-id="f20d5-107">0</span></span>                                                                                       |
|  <span data-ttu-id="f20d5-108">事件源</span><span class="sxs-lookup"><span data-stu-id="f20d5-108">Event Source</span></span>   |                                                                                       <span data-ttu-id="f20d5-109">0</span><span class="sxs-lookup"><span data-stu-id="f20d5-109">0</span></span>                                                                                       |
|    <span data-ttu-id="f20d5-110">组件</span><span class="sxs-lookup"><span data-stu-id="f20d5-110">Component</span></span>    |                                                                                       <span data-ttu-id="f20d5-111">0</span><span class="sxs-lookup"><span data-stu-id="f20d5-111">0</span></span>                                                                                       |
|  <span data-ttu-id="f20d5-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="f20d5-112">Symbolic Name</span></span>  |                                                                                       <span data-ttu-id="f20d5-113">0</span><span class="sxs-lookup"><span data-stu-id="f20d5-113">0</span></span>                                                                                       |
|  <span data-ttu-id="f20d5-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="f20d5-114">Message Text</span></span>   | <span data-ttu-id="f20d5-115">在此 BizTalk 程序集中的业务流程不具有公共接收端口。</span><span class="sxs-lookup"><span data-stu-id="f20d5-115">There are no orchestrations with public receive ports in this BizTalk assembly.</span></span> <span data-ttu-id="f20d5-116">单击后退，并指定 BizTalk 程序集包含业务流程具有公共接收端口</span><span class="sxs-lookup"><span data-stu-id="f20d5-116">Click back and specify a BizTalk assembly containing orchestrations with public receive ports</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="f20d5-117">解释</span><span class="sxs-lookup"><span data-stu-id="f20d5-117">Explanation</span></span>  
 <span data-ttu-id="f20d5-118">此错误表示选择的业务流程不具有公共端口。</span><span class="sxs-lookup"><span data-stu-id="f20d5-118">This error indicates the orchestration selected does not have a public port.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f20d5-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="f20d5-119">User Action</span></span>  
 <span data-ttu-id="f20d5-120">使用以下过程来配置公共端口。</span><span class="sxs-lookup"><span data-stu-id="f20d5-120">Use the following procedure to configure a public port.</span></span>  
  
#### <a name="to-configure-a-public-port"></a><span data-ttu-id="f20d5-121">若要配置的公共端口</span><span class="sxs-lookup"><span data-stu-id="f20d5-121">To configure a public port</span></span>  
  
1.  <span data-ttu-id="f20d5-122">找到业务流程并公开所需接收端口。</span><span class="sxs-lookup"><span data-stu-id="f20d5-122">Locate the orchestration and make the desired receive port public.</span></span>  
  
    1.  <span data-ttu-id="f20d5-123">打开端口配置向导。</span><span class="sxs-lookup"><span data-stu-id="f20d5-123">Open the Port Configuration wizard.</span></span>  
  
    2.  <span data-ttu-id="f20d5-124">在中**选择端口类型**，更改**访问限制**从**内部**（默认值） 到**公有-无限制**。</span><span class="sxs-lookup"><span data-stu-id="f20d5-124">In **Select a Port Type**, change **Access Restrictions** from **Internal** (default) to **Public-no limits**.</span></span>  
  
2.  <span data-ttu-id="f20d5-125">重新编译该程序集。</span><span class="sxs-lookup"><span data-stu-id="f20d5-125">Recompile the assembly.</span></span>  
  
     <span data-ttu-id="f20d5-126">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="f20d5-126">\- OR -</span></span>  
  
     <span data-ttu-id="f20d5-127">加载 BizTalk 程序集具有公共接收端口。</span><span class="sxs-lookup"><span data-stu-id="f20d5-127">Load a BizTalk assembly with public receive ports.</span></span>