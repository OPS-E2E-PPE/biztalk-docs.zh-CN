---
title: 无法导入客户端终结点配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8375e153-ed1c-4bf4-b461-ac026a4b3478
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f3faa6a12bee397edcadb3f15c12a47d763fdce
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987182"
---
# <a name="unable-to-import-client-endpoint-configuration"></a><span data-ttu-id="21469-102">无法导入客户端终结点配置</span><span class="sxs-lookup"><span data-stu-id="21469-102">Unable to import client endpoint configuration</span></span>
## <a name="details"></a><span data-ttu-id="21469-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="21469-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="21469-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="21469-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="21469-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="21469-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="21469-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="21469-106">Event ID</span></span>     |                                         <span data-ttu-id="21469-107">0</span><span class="sxs-lookup"><span data-stu-id="21469-107">0</span></span>                                          |
|  <span data-ttu-id="21469-108">事件源</span><span class="sxs-lookup"><span data-stu-id="21469-108">Event Source</span></span>   |                                         <span data-ttu-id="21469-109">0</span><span class="sxs-lookup"><span data-stu-id="21469-109">0</span></span>                                          |
|    <span data-ttu-id="21469-110">组件</span><span class="sxs-lookup"><span data-stu-id="21469-110">Component</span></span>    |                                         <span data-ttu-id="21469-111">0</span><span class="sxs-lookup"><span data-stu-id="21469-111">0</span></span>                                          |
|  <span data-ttu-id="21469-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="21469-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="21469-113">0</span><span class="sxs-lookup"><span data-stu-id="21469-113">0</span></span>                                          |
|  <span data-ttu-id="21469-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="21469-114">Message Text</span></span>   |                   <span data-ttu-id="21469-115">无法导入客户端终结点配置</span><span class="sxs-lookup"><span data-stu-id="21469-115">Unable to import client endpoint configuration</span></span>                   |
  
## <a name="explanation"></a><span data-ttu-id="21469-116">解释</span><span class="sxs-lookup"><span data-stu-id="21469-116">Explanation</span></span>  
 <span data-ttu-id="21469-117">对于此错误可能有多种解释。</span><span class="sxs-lookup"><span data-stu-id="21469-117">There could be more than one explanation for this error.</span></span> <span data-ttu-id="21469-118">配置文件可能包含无效的字符。</span><span class="sxs-lookup"><span data-stu-id="21469-118">The configuration file may contain invalid characters.</span></span> <span data-ttu-id="21469-119">根元素可能丢失。</span><span class="sxs-lookup"><span data-stu-id="21469-119">The root element may be missing.</span></span> <span data-ttu-id="21469-120">根级别的数据可能无效。</span><span class="sxs-lookup"><span data-stu-id="21469-120">The data at the root level may be invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="21469-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="21469-121">User Action</span></span>  
 <span data-ttu-id="21469-122">验证配置文件是否有效。</span><span class="sxs-lookup"><span data-stu-id="21469-122">Verify the validity of the configuration file.</span></span> <span data-ttu-id="21469-123">尝试使用服务配置编辑器中打开配置文件 (**svcConfigEditor.exe**)，并验证每个属性。</span><span class="sxs-lookup"><span data-stu-id="21469-123">Try to open the configuration file with the Service Configuration Editor (**svcConfigEditor.exe**) and verify each property.</span></span>