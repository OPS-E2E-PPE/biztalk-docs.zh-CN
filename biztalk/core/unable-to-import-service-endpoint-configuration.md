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
ms.openlocfilehash: 85d6fb8006020c47dcec56aa2a173fa36a1aff28
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292756"
---
# <a name="unable-to-import-service-endpoint-configuration"></a><span data-ttu-id="0e780-103">无法导入服务终结点配置。</span><span class="sxs-lookup"><span data-stu-id="0e780-103">Unable to import service endpoint configuration.</span></span>
## <a name="details"></a><span data-ttu-id="0e780-104">详细信息</span><span class="sxs-lookup"><span data-stu-id="0e780-104">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="0e780-105">产品名称</span><span class="sxs-lookup"><span data-stu-id="0e780-105">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="0e780-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="0e780-106">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="0e780-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="0e780-107">Event ID</span></span>     |                                         <span data-ttu-id="0e780-108">0</span><span class="sxs-lookup"><span data-stu-id="0e780-108">0</span></span>                                          |
|  <span data-ttu-id="0e780-109">事件源</span><span class="sxs-lookup"><span data-stu-id="0e780-109">Event Source</span></span>   |                                         <span data-ttu-id="0e780-110">0</span><span class="sxs-lookup"><span data-stu-id="0e780-110">0</span></span>                                          |
|    <span data-ttu-id="0e780-111">组件</span><span class="sxs-lookup"><span data-stu-id="0e780-111">Component</span></span>    |                                         <span data-ttu-id="0e780-112">0</span><span class="sxs-lookup"><span data-stu-id="0e780-112">0</span></span>                                          |
|  <span data-ttu-id="0e780-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="0e780-113">Symbolic Name</span></span>  |                                         <span data-ttu-id="0e780-114">0</span><span class="sxs-lookup"><span data-stu-id="0e780-114">0</span></span>                                          |
|  <span data-ttu-id="0e780-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="0e780-115">Message Text</span></span>   |                  <span data-ttu-id="0e780-116">无法导入服务终结点配置</span><span class="sxs-lookup"><span data-stu-id="0e780-116">Unable to import service endpoint configuration</span></span>                   |
  
## <a name="explanation"></a><span data-ttu-id="0e780-117">解释</span><span class="sxs-lookup"><span data-stu-id="0e780-117">Explanation</span></span>  
 <span data-ttu-id="0e780-118">可能有多个解释此错误。</span><span class="sxs-lookup"><span data-stu-id="0e780-118">There could be more than one explanation for this error.</span></span> <span data-ttu-id="0e780-119">配置文件可能包含无效字符。</span><span class="sxs-lookup"><span data-stu-id="0e780-119">The configuration file may contain invalid characters.</span></span> <span data-ttu-id="0e780-120">可能缺少根元素。</span><span class="sxs-lookup"><span data-stu-id="0e780-120">The root element may be missing.</span></span> <span data-ttu-id="0e780-121">根级别的数据可能无效。</span><span class="sxs-lookup"><span data-stu-id="0e780-121">The data at the root level may be invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="0e780-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="0e780-122">User Action</span></span>  
 <span data-ttu-id="0e780-123">验证配置文件的有效性。</span><span class="sxs-lookup"><span data-stu-id="0e780-123">Verify the validity of the configuration file.</span></span> <span data-ttu-id="0e780-124">尝试使用服务配置编辑器中打开配置文件 (**svcConfigEditor.exe**)，并验证每个属性。</span><span class="sxs-lookup"><span data-stu-id="0e780-124">Try to open the configuration file with the Service Configuration Editor (**svcConfigEditor.exe**) and verify each property.</span></span>