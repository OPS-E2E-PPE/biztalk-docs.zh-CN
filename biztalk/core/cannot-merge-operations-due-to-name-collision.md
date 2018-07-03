---
title: 由于名称冲突无法合并操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 81ddb8b7-6f7e-420c-b7c3-921c0e305326
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57bbb3b085af45ede5632e20f67d5e6c0c4e304e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992318"
---
# <a name="cannot-merge-operations-due-to-name-collision"></a><span data-ttu-id="f6e89-102">由于名称冲突，无法合并操作</span><span class="sxs-lookup"><span data-stu-id="f6e89-102">Cannot merge operations due to name collision</span></span>
## <a name="details"></a><span data-ttu-id="f6e89-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f6e89-103">Details</span></span>  
  
|                 |                                                                                                             |
|-----------------|-------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f6e89-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f6e89-104">Product Name</span></span>   |             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]              |
| <span data-ttu-id="f6e89-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="f6e89-105">Product Version</span></span> |                         [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                          |
|    <span data-ttu-id="f6e89-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f6e89-106">Event ID</span></span>     |                                                      <span data-ttu-id="f6e89-107">0</span><span class="sxs-lookup"><span data-stu-id="f6e89-107">0</span></span>                                                      |
|  <span data-ttu-id="f6e89-108">事件源</span><span class="sxs-lookup"><span data-stu-id="f6e89-108">Event Source</span></span>   |                                                      <span data-ttu-id="f6e89-109">0</span><span class="sxs-lookup"><span data-stu-id="f6e89-109">0</span></span>                                                      |
|    <span data-ttu-id="f6e89-110">组件</span><span class="sxs-lookup"><span data-stu-id="f6e89-110">Component</span></span>    |                                                      <span data-ttu-id="f6e89-111">0</span><span class="sxs-lookup"><span data-stu-id="f6e89-111">0</span></span>                                                      |
|  <span data-ttu-id="f6e89-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="f6e89-112">Symbolic Name</span></span>  |                                                      <span data-ttu-id="f6e89-113">0</span><span class="sxs-lookup"><span data-stu-id="f6e89-113">0</span></span>                                                      |
|  <span data-ttu-id="f6e89-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="f6e89-114">Message Text</span></span>   | <span data-ttu-id="f6e89-115">无法合并操作"{0}"由于名称冲突。</span><span class="sxs-lookup"><span data-stu-id="f6e89-115">Cannot merge operation "{0}" due to name collision.</span></span> <span data-ttu-id="f6e89-116">Web Services 中的所有操作都必须具有唯一的名称。</span><span class="sxs-lookup"><span data-stu-id="f6e89-116">All operations in a web service must have unique names.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="f6e89-117">解释</span><span class="sxs-lookup"><span data-stu-id="f6e89-117">Explanation</span></span>  
 <span data-ttu-id="f6e89-118">此错误表示端口名称或合并的两个不同端口的操作名称具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="f6e89-118">This error indicates the port name or the operation name of two different ports that are being merged have the same name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f6e89-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="f6e89-119">User Action</span></span>  
 <span data-ttu-id="f6e89-120">使用端口配置向导，确保合并的所有端口都具有不同的端口名称和操作。</span><span class="sxs-lookup"><span data-stu-id="f6e89-120">Using the Port Configuration Wizard, ensure that all the ports that are being merged have different port names and operation.</span></span>  
  
 <span data-ttu-id="f6e89-121">有关端口配置的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="f6e89-121">For additional information on port configuration, see the following resource in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="f6e89-122">如何运行端口配置向导</span><span class="sxs-lookup"><span data-stu-id="f6e89-122">How to Run the Port Configuration Wizard</span></span>](../core/how-to-run-the-port-configuration-wizard.md)