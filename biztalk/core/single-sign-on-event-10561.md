---
title: 单一登录：事件 10561 |Microsoft Docs
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
ms.openlocfilehash: ce91071578747053c1966cd208a9251d3fbe835e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398848"
---
# <a name="single-sign-on-event-10561"></a><span data-ttu-id="92dbf-102">单一登录：事件 10561</span><span class="sxs-lookup"><span data-stu-id="92dbf-102">Single Sign-On: Event 10561</span></span>
## <a name="details"></a><span data-ttu-id="92dbf-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="92dbf-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                 |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="92dbf-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="92dbf-104">Product Name</span></span>   |                                                                                                    <span data-ttu-id="92dbf-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="92dbf-105">Enterprise Single Sign-On</span></span>                                                                                                    |
| <span data-ttu-id="92dbf-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="92dbf-106">Product Version</span></span> |                                                                                   [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                    |
|    <span data-ttu-id="92dbf-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="92dbf-107">Event ID</span></span>     |                                                                                                              <span data-ttu-id="92dbf-108">10561</span><span class="sxs-lookup"><span data-stu-id="92dbf-108">10561</span></span>                                                                                                              |
|  <span data-ttu-id="92dbf-109">事件源</span><span class="sxs-lookup"><span data-stu-id="92dbf-109">Event Source</span></span>   |                                                                                                             <span data-ttu-id="92dbf-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="92dbf-110">ENTSSO</span></span>                                                                                                              |
|    <span data-ttu-id="92dbf-111">组件</span><span class="sxs-lookup"><span data-stu-id="92dbf-111">Component</span></span>    |                                                                                                               <span data-ttu-id="92dbf-112">不可用</span><span class="sxs-lookup"><span data-stu-id="92dbf-112">N/A</span></span>                                                                                                               |
|  <span data-ttu-id="92dbf-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="92dbf-113">Symbolic Name</span></span>  |                                                                                                  <span data-ttu-id="92dbf-114">SSO_ERROR_BACKUP_FAILED_MEDIA</span><span class="sxs-lookup"><span data-stu-id="92dbf-114">SSO_ERROR_BACKUP_FAILED_MEDIA</span></span>                                                                                                  |
|  <span data-ttu-id="92dbf-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="92dbf-115">Message Text</span></span>   | <span data-ttu-id="92dbf-116">为主密钥备份指定的文件必须位于 NTFS 文件系统或可移动 media.%r</span><span class="sxs-lookup"><span data-stu-id="92dbf-116">The file specified for backup of the master secrets must be on an NTFS file system or removable media.%r</span></span><br /><br /> <span data-ttu-id="92dbf-117">文件名称: %1 %r</span><span class="sxs-lookup"><span data-stu-id="92dbf-117">File Name: %1%r</span></span><br /><br /> <span data-ttu-id="92dbf-118">客户端用户: %2 %r</span><span class="sxs-lookup"><span data-stu-id="92dbf-118">Client User: %2%r</span></span><br /><br /> <span data-ttu-id="92dbf-119">客户端计算机: %3 %r</span><span class="sxs-lookup"><span data-stu-id="92dbf-119">Client Computer: %3%r</span></span><br /><br /> <span data-ttu-id="92dbf-120">错误代码： %4</span><span class="sxs-lookup"><span data-stu-id="92dbf-120">Error Code: %4</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="92dbf-121">解释</span><span class="sxs-lookup"><span data-stu-id="92dbf-121">Explanation</span></span>  
 <span data-ttu-id="92dbf-122">备份已尝试使用无效的媒体，如 FAT 文件。</span><span class="sxs-lookup"><span data-stu-id="92dbf-122">A backup was attempted using an invalid media, such as a FAT file.</span></span> <span data-ttu-id="92dbf-123">为主密钥备份指定的文件必须位于 NTFS 文件系统或可移动媒体。</span><span class="sxs-lookup"><span data-stu-id="92dbf-123">The file specified for backup of the master secrets must be on an NTFS file system or removable media.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="92dbf-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="92dbf-124">User Action</span></span>  
 <span data-ttu-id="92dbf-125">检查媒体格式，并确保其为 NTFS 或可移动。</span><span class="sxs-lookup"><span data-stu-id="92dbf-125">Check the media format and make sure it is NTFS or removable.</span></span>