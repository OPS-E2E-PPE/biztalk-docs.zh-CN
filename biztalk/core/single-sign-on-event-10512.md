---
title: 单一登录：Event 10512 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4edf0512-112d-40b8-9e29-7dd67f999b6d
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf29293c12a566a82835510e07f23e52ba0ba243
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243388"
---
# <a name="single-sign-on-event-10512"></a><span data-ttu-id="80938-102">单一登录：事件 10512</span><span class="sxs-lookup"><span data-stu-id="80938-102">Single Sign-On: Event 10512</span></span>
## <a name="details"></a><span data-ttu-id="80938-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="80938-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="80938-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="80938-104">Product Name</span></span>   |                 <span data-ttu-id="80938-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="80938-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="80938-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="80938-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="80938-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="80938-107">Event ID</span></span>     |                           <span data-ttu-id="80938-108">10512</span><span class="sxs-lookup"><span data-stu-id="80938-108">10512</span></span>                            |
|  <span data-ttu-id="80938-109">事件源</span><span class="sxs-lookup"><span data-stu-id="80938-109">Event Source</span></span>   |                           <span data-ttu-id="80938-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="80938-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="80938-111">组件</span><span class="sxs-lookup"><span data-stu-id="80938-111">Component</span></span>    |                            <span data-ttu-id="80938-112">N\A</span><span class="sxs-lookup"><span data-stu-id="80938-112">N\A</span></span>                             |
|  <span data-ttu-id="80938-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="80938-113">Symbolic Name</span></span>  |                   <span data-ttu-id="80938-114">SSO_ERROR_LOADLIBRARY</span><span class="sxs-lookup"><span data-stu-id="80938-114">SSO_ERROR_LOADLIBRARY</span></span>                    |
|  <span data-ttu-id="80938-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="80938-115">Message Text</span></span>   |      <span data-ttu-id="80938-116">未能加载 %1 %r</span><span class="sxs-lookup"><span data-stu-id="80938-116">Failed to load %1%r</span></span><br /><br /> <span data-ttu-id="80938-117">错误代码: %2。</span><span class="sxs-lookup"><span data-stu-id="80938-117">Error code: %2.</span></span>       |

## <a name="explanation"></a><span data-ttu-id="80938-118">解释</span><span class="sxs-lookup"><span data-stu-id="80938-118">Explanation</span></span>  
 <span data-ttu-id="80938-119">此错误事件表示不可能将指定的动态链接库 (DLL) 加载到 SSO 服务器进程。</span><span class="sxs-lookup"><span data-stu-id="80938-119">This Error event indicates that the specified Dynamic Link Library (DLL) could not be loaded into the SSO server process.</span></span> <span data-ttu-id="80938-120">如果 DLL 缺少在 SSO 安装目录中，通常 C:\Program Files\Common Files\Enterprise Single Sign-on，则可能表示未正确，完成安装程序，或在安装完成后删除了 DLL 已完成。</span><span class="sxs-lookup"><span data-stu-id="80938-120">If the DLL is missing in the SSO installation directory, typically C:\Program Files\Common Files\Enterprise Single Sign-On, it may indicate that setup was not completed correctly, or that the DLL was deleted after setup was completed.</span></span> <span data-ttu-id="80938-121">如果 DLL 存在，则可能会存在 SSO 服务将正确路径解析到 DLL 的问题。</span><span class="sxs-lookup"><span data-stu-id="80938-121">If the DLL is present, then there could be a problem with the SSO service resolving the correct path to the DLL.</span></span> <span data-ttu-id="80938-122">此外，DLL 本身也可能损坏。</span><span class="sxs-lookup"><span data-stu-id="80938-122">Additionally, the DLL itself could be corrupted.</span></span>  

## <a name="user-action"></a><span data-ttu-id="80938-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="80938-123">User Action</span></span>  
 <span data-ttu-id="80938-124">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="80938-124">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="80938-125">如果更广的故障可能有必要，卸载并重新安装该产品怀疑安装程序。</span><span class="sxs-lookup"><span data-stu-id="80938-125">If a wider failure of setup is suspected it may be necessary to uninstall and reinstall the product.</span></span>  

- <span data-ttu-id="80938-126">如果单个 DLL 已丢失或损坏，尝试将其替换为，然后重新启动该服务。</span><span class="sxs-lookup"><span data-stu-id="80938-126">If the single DLL is missing or corrupted, attempt to replace it and then restart the service.</span></span>  

  <span data-ttu-id="80938-127">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="80938-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="80938-128">实现企业单一登录</span><span class="sxs-lookup"><span data-stu-id="80938-128">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)
