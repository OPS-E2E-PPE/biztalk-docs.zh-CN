---
title: "无法导入客户端终结点配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8375e153-ed1c-4bf4-b461-ac026a4b3478
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 30be7958ca07dde47d147711da06a276e86ff714
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-import-client-endpoint-configuration"></a><span data-ttu-id="7f383-102">无法导入客户端终结点配置</span><span class="sxs-lookup"><span data-stu-id="7f383-102">Unable to import client endpoint configuration</span></span>
## <a name="details"></a><span data-ttu-id="7f383-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="7f383-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7f383-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="7f383-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="7f383-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="7f383-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="7f383-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="7f383-106">Event ID</span></span>|<span data-ttu-id="7f383-107">0</span><span class="sxs-lookup"><span data-stu-id="7f383-107">0</span></span>|  
|<span data-ttu-id="7f383-108">事件源</span><span class="sxs-lookup"><span data-stu-id="7f383-108">Event Source</span></span>|<span data-ttu-id="7f383-109">0</span><span class="sxs-lookup"><span data-stu-id="7f383-109">0</span></span>|  
|<span data-ttu-id="7f383-110">组件</span><span class="sxs-lookup"><span data-stu-id="7f383-110">Component</span></span>|<span data-ttu-id="7f383-111">0</span><span class="sxs-lookup"><span data-stu-id="7f383-111">0</span></span>|  
|<span data-ttu-id="7f383-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="7f383-112">Symbolic Name</span></span>|<span data-ttu-id="7f383-113">0</span><span class="sxs-lookup"><span data-stu-id="7f383-113">0</span></span>|  
|<span data-ttu-id="7f383-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="7f383-114">Message Text</span></span>|<span data-ttu-id="7f383-115">无法导入客户端终结点配置</span><span class="sxs-lookup"><span data-stu-id="7f383-115">Unable to import client endpoint configuration</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7f383-116">解释</span><span class="sxs-lookup"><span data-stu-id="7f383-116">Explanation</span></span>  
 <span data-ttu-id="7f383-117">对于此错误可能有多种解释。</span><span class="sxs-lookup"><span data-stu-id="7f383-117">There could be more than one explanation for this error.</span></span> <span data-ttu-id="7f383-118">配置文件可能包含无效的字符。</span><span class="sxs-lookup"><span data-stu-id="7f383-118">The configuration file may contain invalid characters.</span></span> <span data-ttu-id="7f383-119">根元素可能丢失。</span><span class="sxs-lookup"><span data-stu-id="7f383-119">The root element may be missing.</span></span> <span data-ttu-id="7f383-120">根级别的数据可能无效。</span><span class="sxs-lookup"><span data-stu-id="7f383-120">The data at the root level may be invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7f383-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="7f383-121">User Action</span></span>  
 <span data-ttu-id="7f383-122">验证配置文件是否有效。</span><span class="sxs-lookup"><span data-stu-id="7f383-122">Verify the validity of the configuration file.</span></span> <span data-ttu-id="7f383-123">尝试打开用服务配置编辑器中的配置文件 (**svcConfigEditor.exe**) 并验证每个属性。</span><span class="sxs-lookup"><span data-stu-id="7f383-123">Try to open the configuration file with the Service Configuration Editor (**svcConfigEditor.exe**) and verify each property.</span></span>