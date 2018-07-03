---
title: 单一登录： 事件 10759 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5347f3d6-d31a-4c00-a64c-c0b0f680de88
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 177b5d1383a583ddc33a67a7290bff98b1d13364
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36967582"
---
# <a name="single-sign-on-event-10759"></a><span data-ttu-id="04e0d-102">单一登录： 事件 10759</span><span class="sxs-lookup"><span data-stu-id="04e0d-102">Single Sign-On: Event 10759</span></span>
## <a name="details"></a><span data-ttu-id="04e0d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="04e0d-103">Details</span></span>  
  
|                 |                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="04e0d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="04e0d-104">Product Name</span></span>   |                                             <span data-ttu-id="04e0d-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="04e0d-105">Enterprise Single Sign-On</span></span>                                             |
| <span data-ttu-id="04e0d-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="04e0d-106">Product Version</span></span> |                            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                             |
|    <span data-ttu-id="04e0d-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="04e0d-107">Event ID</span></span>     |                                                       <span data-ttu-id="04e0d-108">10759</span><span class="sxs-lookup"><span data-stu-id="04e0d-108">10759</span></span>                                                       |
|  <span data-ttu-id="04e0d-109">事件源</span><span class="sxs-lookup"><span data-stu-id="04e0d-109">Event Source</span></span>   |                                                      <span data-ttu-id="04e0d-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="04e0d-110">ENTSSO</span></span>                                                       |
|    <span data-ttu-id="04e0d-111">组件</span><span class="sxs-lookup"><span data-stu-id="04e0d-111">Component</span></span>    |                                                        <span data-ttu-id="04e0d-112">N/A</span><span class="sxs-lookup"><span data-stu-id="04e0d-112">N/A</span></span>                                                        |
|  <span data-ttu-id="04e0d-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="04e0d-113">Symbolic Name</span></span>  |                                       <span data-ttu-id="04e0d-114">ENTSSO_E_BACKUP_RESTORE_FAILED_MEDIA</span><span class="sxs-lookup"><span data-stu-id="04e0d-114">ENTSSO_E_BACKUP_RESTORE_FAILED_MEDIA</span></span>                                        |
|  <span data-ttu-id="04e0d-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="04e0d-115">Message Text</span></span>   | <span data-ttu-id="04e0d-116">指定用于备份或还原主密钥的文件必须位于 NTFS 文件系统或可移动介质上。</span><span class="sxs-lookup"><span data-stu-id="04e0d-116">The file specified for backup or restore of the master secrets must be on an NTFS file system or removable media.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="04e0d-117">解释</span><span class="sxs-lookup"><span data-stu-id="04e0d-117">Explanation</span></span>  
 <span data-ttu-id="04e0d-118">只有 NTFS 文件系统或可移动介质能够受到保护。</span><span class="sxs-lookup"><span data-stu-id="04e0d-118">Only NTFS file systems or removable media can be secured.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="04e0d-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="04e0d-119">User Action</span></span>  
 <span data-ttu-id="04e0d-120">切换到 NTFS 文件系统或可移动介质以备份主密钥。</span><span class="sxs-lookup"><span data-stu-id="04e0d-120">Switch to either an NTFS file system of removable media to back up the master secret.</span></span>