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
ms.openlocfilehash: 8337af0d97eaf3ba8b1737ca8641389bda984cee
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292745"
---
# <a name="unable-to-import-client-endpoint-configuration"></a><span data-ttu-id="397a2-102">无法导入客户端终结点配置</span><span class="sxs-lookup"><span data-stu-id="397a2-102">Unable to import client endpoint configuration</span></span>
## <a name="details"></a><span data-ttu-id="397a2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="397a2-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="397a2-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="397a2-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="397a2-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="397a2-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="397a2-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="397a2-106">Event ID</span></span>     |                                         <span data-ttu-id="397a2-107">0</span><span class="sxs-lookup"><span data-stu-id="397a2-107">0</span></span>                                          |
|  <span data-ttu-id="397a2-108">事件源</span><span class="sxs-lookup"><span data-stu-id="397a2-108">Event Source</span></span>   |                                         <span data-ttu-id="397a2-109">0</span><span class="sxs-lookup"><span data-stu-id="397a2-109">0</span></span>                                          |
|    <span data-ttu-id="397a2-110">组件</span><span class="sxs-lookup"><span data-stu-id="397a2-110">Component</span></span>    |                                         <span data-ttu-id="397a2-111">0</span><span class="sxs-lookup"><span data-stu-id="397a2-111">0</span></span>                                          |
|  <span data-ttu-id="397a2-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="397a2-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="397a2-113">0</span><span class="sxs-lookup"><span data-stu-id="397a2-113">0</span></span>                                          |
|  <span data-ttu-id="397a2-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="397a2-114">Message Text</span></span>   |                   <span data-ttu-id="397a2-115">无法导入客户端终结点配置</span><span class="sxs-lookup"><span data-stu-id="397a2-115">Unable to import client endpoint configuration</span></span>                   |
  
## <a name="explanation"></a><span data-ttu-id="397a2-116">解释</span><span class="sxs-lookup"><span data-stu-id="397a2-116">Explanation</span></span>  
 <span data-ttu-id="397a2-117">可能有多个解释此错误。</span><span class="sxs-lookup"><span data-stu-id="397a2-117">There could be more than one explanation for this error.</span></span> <span data-ttu-id="397a2-118">配置文件可能包含无效字符。</span><span class="sxs-lookup"><span data-stu-id="397a2-118">The configuration file may contain invalid characters.</span></span> <span data-ttu-id="397a2-119">可能缺少根元素。</span><span class="sxs-lookup"><span data-stu-id="397a2-119">The root element may be missing.</span></span> <span data-ttu-id="397a2-120">根级别的数据可能无效。</span><span class="sxs-lookup"><span data-stu-id="397a2-120">The data at the root level may be invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="397a2-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="397a2-121">User Action</span></span>  
 <span data-ttu-id="397a2-122">验证配置文件的有效性。</span><span class="sxs-lookup"><span data-stu-id="397a2-122">Verify the validity of the configuration file.</span></span> <span data-ttu-id="397a2-123">尝试使用服务配置编辑器中打开配置文件 (**svcConfigEditor.exe**)，并验证每个属性。</span><span class="sxs-lookup"><span data-stu-id="397a2-123">Try to open the configuration file with the Service Configuration Editor (**svcConfigEditor.exe**) and verify each property.</span></span>