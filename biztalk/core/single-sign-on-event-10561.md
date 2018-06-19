---
title: 单一登录： 事件 10561 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 770e6fc1-0854-4555-8f2a-5f199e3aaca7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5148633c7fffabe0ef4bb4789fe4ded58336c10
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22270733"
---
# <a name="single-sign-on-event-10561"></a><span data-ttu-id="23157-102">单一登录： 事件 10561</span><span class="sxs-lookup"><span data-stu-id="23157-102">Single Sign-On: Event 10561</span></span>
## <a name="details"></a><span data-ttu-id="23157-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="23157-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="23157-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="23157-104">Product Name</span></span>|<span data-ttu-id="23157-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="23157-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="23157-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="23157-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="23157-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="23157-107">Event ID</span></span>|<span data-ttu-id="23157-108">10561</span><span class="sxs-lookup"><span data-stu-id="23157-108">10561</span></span>|  
|<span data-ttu-id="23157-109">事件源</span><span class="sxs-lookup"><span data-stu-id="23157-109">Event Source</span></span>|<span data-ttu-id="23157-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="23157-110">ENTSSO</span></span>|  
|<span data-ttu-id="23157-111">组件</span><span class="sxs-lookup"><span data-stu-id="23157-111">Component</span></span>|<span data-ttu-id="23157-112">N/A</span><span class="sxs-lookup"><span data-stu-id="23157-112">N/A</span></span>|  
|<span data-ttu-id="23157-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="23157-113">Symbolic Name</span></span>|<span data-ttu-id="23157-114">SSO_ERROR_BACKUP_FAILED_MEDIA</span><span class="sxs-lookup"><span data-stu-id="23157-114">SSO_ERROR_BACKUP_FAILED_MEDIA</span></span>|  
|<span data-ttu-id="23157-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="23157-115">Message Text</span></span>|<span data-ttu-id="23157-116">为主密钥备份指定的文件必须位于 NTFS 文件系统或可移动媒体上。%r</span><span class="sxs-lookup"><span data-stu-id="23157-116">The file specified for backup of the master secrets must be on an NTFS file system or removable media.%r</span></span><br /><br /> <span data-ttu-id="23157-117">文件名: %1 %r</span><span class="sxs-lookup"><span data-stu-id="23157-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="23157-118">客户端用户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="23157-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="23157-119">客户端计算机: %3 %r</span><span class="sxs-lookup"><span data-stu-id="23157-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="23157-120">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="23157-120">Error Code: %4</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="23157-121">解释</span><span class="sxs-lookup"><span data-stu-id="23157-121">Explanation</span></span>  
 <span data-ttu-id="23157-122">尝试备份所使用的媒体（如 FAT 文件）无效。</span><span class="sxs-lookup"><span data-stu-id="23157-122">A backup was attempted using an invalid media, such as a FAT file.</span></span> <span data-ttu-id="23157-123">为主密钥备份指定的文件必须位于 NTFS 文件系统或可移动媒体上。</span><span class="sxs-lookup"><span data-stu-id="23157-123">The file specified for backup of the master secrets must be on an NTFS file system or removable media.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="23157-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="23157-124">User Action</span></span>  
 <span data-ttu-id="23157-125">检查媒体的格式，确保其为 NTFS 格式或可移动媒体。</span><span class="sxs-lookup"><span data-stu-id="23157-125">Check the media format and make sure it is NTFS or removable.</span></span>