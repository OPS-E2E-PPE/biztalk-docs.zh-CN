---
title: "单一登录： 事件 10759 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5347f3d6-d31a-4c00-a64c-c0b0f680de88
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 81ff42b71499df5848a55848b3dc1067adb830bd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="single-sign-on-event-10759"></a><span data-ttu-id="5cc8f-102">单一登录： 事件 10759</span><span class="sxs-lookup"><span data-stu-id="5cc8f-102">Single Sign-On: Event 10759</span></span>
## <a name="details"></a><span data-ttu-id="5cc8f-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5cc8f-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5cc8f-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5cc8f-104">Product Name</span></span>|<span data-ttu-id="5cc8f-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="5cc8f-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="5cc8f-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="5cc8f-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="5cc8f-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5cc8f-107">Event ID</span></span>|<span data-ttu-id="5cc8f-108">10759</span><span class="sxs-lookup"><span data-stu-id="5cc8f-108">10759</span></span>|  
|<span data-ttu-id="5cc8f-109">事件源</span><span class="sxs-lookup"><span data-stu-id="5cc8f-109">Event Source</span></span>|<span data-ttu-id="5cc8f-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="5cc8f-110">ENTSSO</span></span>|  
|<span data-ttu-id="5cc8f-111">组件</span><span class="sxs-lookup"><span data-stu-id="5cc8f-111">Component</span></span>|<span data-ttu-id="5cc8f-112">N/A</span><span class="sxs-lookup"><span data-stu-id="5cc8f-112">N/A</span></span>|  
|<span data-ttu-id="5cc8f-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="5cc8f-113">Symbolic Name</span></span>|<span data-ttu-id="5cc8f-114">ENTSSO_E_BACKUP_RESTORE_FAILED_MEDIA</span><span class="sxs-lookup"><span data-stu-id="5cc8f-114">ENTSSO_E_BACKUP_RESTORE_FAILED_MEDIA</span></span>|  
|<span data-ttu-id="5cc8f-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="5cc8f-115">Message Text</span></span>|<span data-ttu-id="5cc8f-116">指定用于备份或还原主密钥的文件必须位于 NTFS 文件系统或可移动介质上。</span><span class="sxs-lookup"><span data-stu-id="5cc8f-116">The file specified for backup or restore of the master secrets must be on an NTFS file system or removable media.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5cc8f-117">解释</span><span class="sxs-lookup"><span data-stu-id="5cc8f-117">Explanation</span></span>  
 <span data-ttu-id="5cc8f-118">只有 NTFS 文件系统或可移动介质能够受到保护。</span><span class="sxs-lookup"><span data-stu-id="5cc8f-118">Only NTFS file systems or removable media can be secured.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5cc8f-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="5cc8f-119">User Action</span></span>  
 <span data-ttu-id="5cc8f-120">切换到 NTFS 文件系统或可移动介质以备份主密钥。</span><span class="sxs-lookup"><span data-stu-id="5cc8f-120">Switch to either an NTFS file system of removable media to back up the master secret.</span></span>