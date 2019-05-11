---
title: 文档规范类型找不到 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2cb2a458-d0f4-420d-8d35-0e739167464f
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5b4c63f34d28bf3f53e34f44373d14f6cd6b979f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389346"
---
# <a name="document-spec-type-not-found"></a><span data-ttu-id="9c613-102">找不到文档规格类型</span><span class="sxs-lookup"><span data-stu-id="9c613-102">Document spec type not found</span></span>
## <a name="details"></a><span data-ttu-id="9c613-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="9c613-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="9c613-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="9c613-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="9c613-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="9c613-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="9c613-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="9c613-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="9c613-107">事件源</span><span class="sxs-lookup"><span data-stu-id="9c613-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="9c613-108">EDI</span><span class="sxs-lookup"><span data-stu-id="9c613-108">EDI</span></span> |
|    <span data-ttu-id="9c613-109">组件</span><span class="sxs-lookup"><span data-stu-id="9c613-109">Component</span></span>    |                                       <span data-ttu-id="9c613-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="9c613-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="9c613-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="9c613-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="9c613-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="9c613-112">Message Text</span></span>   |                            <span data-ttu-id="9c613-113">文档规范类型{0}找不到</span><span class="sxs-lookup"><span data-stu-id="9c613-113">Document spec type {0} not found</span></span>                            |
  
## <a name="explanation"></a><span data-ttu-id="9c613-114">解释</span><span class="sxs-lookup"><span data-stu-id="9c613-114">Explanation</span></span>  
 <span data-ttu-id="9c613-115">此错误指示找不到架构。</span><span class="sxs-lookup"><span data-stu-id="9c613-115">This error indicates the schema is not found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="9c613-116">用户操作</span><span class="sxs-lookup"><span data-stu-id="9c613-116">User Action</span></span>  
 <span data-ttu-id="9c613-117">若要解决此错误，部署文档架构：</span><span class="sxs-lookup"><span data-stu-id="9c613-117">To resolve this error, deploy the document schema:</span></span>  
  
1.  <span data-ttu-id="9c613-118">启动**Microsoft Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="9c613-118">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="9c613-119">创建或打开现有项目</span><span class="sxs-lookup"><span data-stu-id="9c613-119">Create or open an existing project</span></span>  
  
3.  <span data-ttu-id="9c613-120">将架构添加到项目。</span><span class="sxs-lookup"><span data-stu-id="9c613-120">Add the schema to the project.</span></span>  
  
4.  <span data-ttu-id="9c613-121">部署 Visual Studio 中的项目。</span><span class="sxs-lookup"><span data-stu-id="9c613-121">Deploy the project in Visual Studio.</span></span>