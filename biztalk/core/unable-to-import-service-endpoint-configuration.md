---
title: 无法导入服务终结点配置。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6dae5154-04e2-4d9b-b2b2-85313683fd9e
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4100435706ab26c0f4ab99dea4d2088ecad1c948
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286717"
---
# <a name="unable-to-import-service-endpoint-configuration"></a><span data-ttu-id="28622-103">无法导入服务终结点配置。</span><span class="sxs-lookup"><span data-stu-id="28622-103">Unable to import service endpoint configuration.</span></span>
## <a name="details"></a><span data-ttu-id="28622-104">详细信息</span><span class="sxs-lookup"><span data-stu-id="28622-104">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="28622-105">产品名称</span><span class="sxs-lookup"><span data-stu-id="28622-105">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="28622-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="28622-106">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="28622-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="28622-107">Event ID</span></span>|<span data-ttu-id="28622-108">0</span><span class="sxs-lookup"><span data-stu-id="28622-108">0</span></span>|  
|<span data-ttu-id="28622-109">事件源</span><span class="sxs-lookup"><span data-stu-id="28622-109">Event Source</span></span>|<span data-ttu-id="28622-110">0</span><span class="sxs-lookup"><span data-stu-id="28622-110">0</span></span>|  
|<span data-ttu-id="28622-111">组件</span><span class="sxs-lookup"><span data-stu-id="28622-111">Component</span></span>|<span data-ttu-id="28622-112">0</span><span class="sxs-lookup"><span data-stu-id="28622-112">0</span></span>|  
|<span data-ttu-id="28622-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="28622-113">Symbolic Name</span></span>|<span data-ttu-id="28622-114">0</span><span class="sxs-lookup"><span data-stu-id="28622-114">0</span></span>|  
|<span data-ttu-id="28622-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="28622-115">Message Text</span></span>|<span data-ttu-id="28622-116">无法导入服务终结点配置</span><span class="sxs-lookup"><span data-stu-id="28622-116">Unable to import service endpoint configuration</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="28622-117">解释</span><span class="sxs-lookup"><span data-stu-id="28622-117">Explanation</span></span>  
 <span data-ttu-id="28622-118">对于此错误可能有多种解释。</span><span class="sxs-lookup"><span data-stu-id="28622-118">There could be more than one explanation for this error.</span></span> <span data-ttu-id="28622-119">配置文件可能包含无效的字符。</span><span class="sxs-lookup"><span data-stu-id="28622-119">The configuration file may contain invalid characters.</span></span> <span data-ttu-id="28622-120">根元素可能丢失。</span><span class="sxs-lookup"><span data-stu-id="28622-120">The root element may be missing.</span></span> <span data-ttu-id="28622-121">根级别的数据可能无效。</span><span class="sxs-lookup"><span data-stu-id="28622-121">The data at the root level may be invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="28622-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="28622-122">User Action</span></span>  
 <span data-ttu-id="28622-123">验证配置文件是否有效。</span><span class="sxs-lookup"><span data-stu-id="28622-123">Verify the validity of the configuration file.</span></span> <span data-ttu-id="28622-124">尝试打开用服务配置编辑器中的配置文件 (**svcConfigEditor.exe**) 并验证每个属性。</span><span class="sxs-lookup"><span data-stu-id="28622-124">Try to open the configuration file with the Service Configuration Editor (**svcConfigEditor.exe**) and verify each property.</span></span>