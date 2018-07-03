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
ms.openlocfilehash: 46b8bffb132921e7b939f251db21e0c6c7839dc2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014222"
---
# <a name="document-spec-type-not-found"></a><span data-ttu-id="c42cf-102">找不到文档规格类型</span><span class="sxs-lookup"><span data-stu-id="c42cf-102">Document spec type not found</span></span>
## <a name="details"></a><span data-ttu-id="c42cf-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c42cf-103">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="c42cf-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c42cf-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="c42cf-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="c42cf-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="c42cf-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c42cf-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="c42cf-107">事件源</span><span class="sxs-lookup"><span data-stu-id="c42cf-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="c42cf-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="c42cf-108"> EDI</span></span> |
|    <span data-ttu-id="c42cf-109">组件</span><span class="sxs-lookup"><span data-stu-id="c42cf-109">Component</span></span>    |                                       <span data-ttu-id="c42cf-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="c42cf-110">EDI Engine</span></span>                                       |
|  <span data-ttu-id="c42cf-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="c42cf-111">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="c42cf-112">消息正文</span><span class="sxs-lookup"><span data-stu-id="c42cf-112">Message Text</span></span>   |                            <span data-ttu-id="c42cf-113">文档规范类型{0}找不到</span><span class="sxs-lookup"><span data-stu-id="c42cf-113">Document spec type {0} not found</span></span>                            |
  
## <a name="explanation"></a><span data-ttu-id="c42cf-114">解释</span><span class="sxs-lookup"><span data-stu-id="c42cf-114">Explanation</span></span>  
 <span data-ttu-id="c42cf-115">此错误表明未找到架构。</span><span class="sxs-lookup"><span data-stu-id="c42cf-115">This error indicates the schema is not found.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c42cf-116">用户操作</span><span class="sxs-lookup"><span data-stu-id="c42cf-116">User Action</span></span>  
 <span data-ttu-id="c42cf-117">若要解决此错误，请部署该文档架构：</span><span class="sxs-lookup"><span data-stu-id="c42cf-117">To resolve this error, deploy the document schema:</span></span>  
  
1.  <span data-ttu-id="c42cf-118">启动**Microsoft Visual Studio**。</span><span class="sxs-lookup"><span data-stu-id="c42cf-118">Start **Microsoft Visual Studio**.</span></span>  
  
2.  <span data-ttu-id="c42cf-119">创建或打开现有项目</span><span class="sxs-lookup"><span data-stu-id="c42cf-119">Create or open an existing project</span></span>  
  
3.  <span data-ttu-id="c42cf-120">将架构添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="c42cf-120">Add the schema to the project.</span></span>  
  
4.  <span data-ttu-id="c42cf-121">在 Visual Studio 中部署项目。</span><span class="sxs-lookup"><span data-stu-id="c42cf-121">Deploy the project in Visual Studio.</span></span>