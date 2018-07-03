---
title: 命名空间中找不到类型 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 66387fa6-3ba3-499f-99d6-bb0033c68adc
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8b369b3ce29b989f01f0ea95d6f32a663d7e7bc5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980758"
---
# <a name="type-cannot-be-found-in-namespace"></a><span data-ttu-id="715c2-102">命名空间中找不到类型</span><span class="sxs-lookup"><span data-stu-id="715c2-102">Type cannot be found in namespace</span></span>
## <a name="details"></a><span data-ttu-id="715c2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="715c2-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="715c2-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="715c2-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="715c2-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="715c2-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="715c2-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="715c2-106">Event ID</span></span>     |                                         <span data-ttu-id="715c2-107">0</span><span class="sxs-lookup"><span data-stu-id="715c2-107">0</span></span>                                          |
|  <span data-ttu-id="715c2-108">事件源</span><span class="sxs-lookup"><span data-stu-id="715c2-108">Event Source</span></span>   |                                         <span data-ttu-id="715c2-109">0</span><span class="sxs-lookup"><span data-stu-id="715c2-109">0</span></span>                                          |
|    <span data-ttu-id="715c2-110">组件</span><span class="sxs-lookup"><span data-stu-id="715c2-110">Component</span></span>    |                                         <span data-ttu-id="715c2-111">0</span><span class="sxs-lookup"><span data-stu-id="715c2-111">0</span></span>                                          |
|  <span data-ttu-id="715c2-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="715c2-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="715c2-113">0</span><span class="sxs-lookup"><span data-stu-id="715c2-113">0</span></span>                                          |
|  <span data-ttu-id="715c2-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="715c2-114">Message Text</span></span>   |                <span data-ttu-id="715c2-115">错误： 类型"{0}"不能在命名空间中找到"{1}"</span><span class="sxs-lookup"><span data-stu-id="715c2-115">Error: Type "{0}" cannot be found in namespace "{1}"</span></span>                |
  
## <a name="explanation"></a><span data-ttu-id="715c2-116">解释</span><span class="sxs-lookup"><span data-stu-id="715c2-116">Explanation</span></span>  
 <span data-ttu-id="715c2-117">此错误表示所创建的项目参考的是无法在指定的命名空间中找到的类型。</span><span class="sxs-lookup"><span data-stu-id="715c2-117">This error indicates artifacts that are created are referencing types which cannot be found in the namespace specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="715c2-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="715c2-118">User Action</span></span>  
 <span data-ttu-id="715c2-119">添加包含无法找到的类型的引用，然后再次运行向导（如果您拥有要尝试使用的 WCF 服务）。</span><span class="sxs-lookup"><span data-stu-id="715c2-119">Add a reference that contain the type that is not found, and run the wizard again (if you own the WCF service that you are trying to consume).</span></span> <span data-ttu-id="715c2-120">否则，请与服务提供商联系。</span><span class="sxs-lookup"><span data-stu-id="715c2-120">Otherwise, contact the service provider.</span></span>