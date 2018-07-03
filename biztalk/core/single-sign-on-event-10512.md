---
title: 单一登录： 事件 10512 |Microsoft Docs
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
ms.openlocfilehash: 54ba5a340a1a7590dae72016a3e747726ea68125
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980958"
---
# <a name="single-sign-on-event-10512"></a><span data-ttu-id="9708b-102">单一登录： 事件 10512</span><span class="sxs-lookup"><span data-stu-id="9708b-102">Single Sign-On: Event 10512</span></span>
## <a name="details"></a><span data-ttu-id="9708b-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="9708b-103">Details</span></span>  

|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="9708b-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="9708b-104">Product Name</span></span>   |                 <span data-ttu-id="9708b-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="9708b-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="9708b-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="9708b-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="9708b-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="9708b-107">Event ID</span></span>     |                           <span data-ttu-id="9708b-108">10512</span><span class="sxs-lookup"><span data-stu-id="9708b-108">10512</span></span>                            |
|  <span data-ttu-id="9708b-109">事件源</span><span class="sxs-lookup"><span data-stu-id="9708b-109">Event Source</span></span>   |                           <span data-ttu-id="9708b-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="9708b-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="9708b-111">组件</span><span class="sxs-lookup"><span data-stu-id="9708b-111">Component</span></span>    |                            <span data-ttu-id="9708b-112">N\A</span><span class="sxs-lookup"><span data-stu-id="9708b-112">N\A</span></span>                             |
|  <span data-ttu-id="9708b-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="9708b-113">Symbolic Name</span></span>  |                   <span data-ttu-id="9708b-114">SSO_ERROR_LOADLIBRARY</span><span class="sxs-lookup"><span data-stu-id="9708b-114">SSO_ERROR_LOADLIBRARY</span></span>                    |
|  <span data-ttu-id="9708b-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="9708b-115">Message Text</span></span>   |      <span data-ttu-id="9708b-116">无法加载 %1%r</span><span class="sxs-lookup"><span data-stu-id="9708b-116">Failed to load %1%r</span></span><br /><br /> <span data-ttu-id="9708b-117">错误代码: %2。</span><span class="sxs-lookup"><span data-stu-id="9708b-117">Error code: %2.</span></span>       |

## <a name="explanation"></a><span data-ttu-id="9708b-118">解释</span><span class="sxs-lookup"><span data-stu-id="9708b-118">Explanation</span></span>  
 <span data-ttu-id="9708b-119">此错误事件表明指定的动态链接库 (DLL) 无法加载到 SSO 服务器进程中。</span><span class="sxs-lookup"><span data-stu-id="9708b-119">This Error event indicates that the specified Dynamic Link Library (DLL) could not be loaded into the SSO server process.</span></span> <span data-ttu-id="9708b-120">如果 SSO 安装目录（通常为 C:\Program Files\Common Files\Enterprise Single Sign-On）中丢失 DLL，则可能表明未正确完成安装，或者在安装完成后删除了 DLL。</span><span class="sxs-lookup"><span data-stu-id="9708b-120">If the DLL is missing in the SSO installation directory, typically C:\Program Files\Common Files\Enterprise Single Sign-On, it may indicate that setup was not completed correctly, or that the DLL was deleted after setup was completed.</span></span> <span data-ttu-id="9708b-121">如果 DLL 存在，则 SSO 服务将正确路径解析到 DLL 时可能出现问题。</span><span class="sxs-lookup"><span data-stu-id="9708b-121">If the DLL is present, then there could be a problem with the SSO service resolving the correct path to the DLL.</span></span> <span data-ttu-id="9708b-122">此外，DLL 本身也可能损坏。</span><span class="sxs-lookup"><span data-stu-id="9708b-122">Additionally, the DLL itself could be corrupted.</span></span>  

## <a name="user-action"></a><span data-ttu-id="9708b-123">用户操作</span><span class="sxs-lookup"><span data-stu-id="9708b-123">User Action</span></span>  
 <span data-ttu-id="9708b-124">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="9708b-124">To resolve this error, do one or more of the following:</span></span>  

- <span data-ttu-id="9708b-125">如果怀疑出现更大范围的安装失败，则可能必须卸载并重新安装产品。</span><span class="sxs-lookup"><span data-stu-id="9708b-125">If a wider failure of setup is suspected it may be necessary to uninstall and reinstall the product.</span></span>  

- <span data-ttu-id="9708b-126">如果一个 DLL 丢失或损坏，请尝试将其替换，然后重新启动服务。</span><span class="sxs-lookup"><span data-stu-id="9708b-126">If the single DLL is missing or corrupted, attempt to replace it and then restart the service.</span></span>  

  <span data-ttu-id="9708b-127">有关详细信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="9708b-127">For more information, see the following resources in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  

- [<span data-ttu-id="9708b-128">实现企业单一登录</span><span class="sxs-lookup"><span data-stu-id="9708b-128">Implementing Enterprise Single Sign-On</span></span>](../core/implementing-enterprise-single-sign-on.md)
