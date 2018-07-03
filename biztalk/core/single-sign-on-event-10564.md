---
title: 单一登录： 事件 10564 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e523c97a-608e-4bf4-8747-cfa0cce10acf
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8be4ea87757a1fa0cb5d8ebd2e344ce521dbf740
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997142"
---
# <a name="single-sign-on-event-10564"></a><span data-ttu-id="c2c4e-102">单一登录： 事件 10564</span><span class="sxs-lookup"><span data-stu-id="c2c4e-102">Single Sign-On: Event 10564</span></span>
## <a name="details"></a><span data-ttu-id="c2c4e-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="c2c4e-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="c2c4e-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="c2c4e-104">Product Name</span></span>   |                 <span data-ttu-id="c2c4e-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="c2c4e-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="c2c4e-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="c2c4e-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="c2c4e-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="c2c4e-107">Event ID</span></span>     |                           <span data-ttu-id="c2c4e-108">10564</span><span class="sxs-lookup"><span data-stu-id="c2c4e-108">10564</span></span>                            |
|  <span data-ttu-id="c2c4e-109">事件源</span><span class="sxs-lookup"><span data-stu-id="c2c4e-109">Event Source</span></span>   |                           <span data-ttu-id="c2c4e-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="c2c4e-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="c2c4e-111">组件</span><span class="sxs-lookup"><span data-stu-id="c2c4e-111">Component</span></span>    |                            <span data-ttu-id="c2c4e-112">N/A</span><span class="sxs-lookup"><span data-stu-id="c2c4e-112">N/A</span></span>                             |
|  <span data-ttu-id="c2c4e-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="c2c4e-113">Symbolic Name</span></span>  |           <span data-ttu-id="c2c4e-114">SSO_ERROR_BACKUP_FILE_INCORRECT_FORMAT</span><span class="sxs-lookup"><span data-stu-id="c2c4e-114">SSO_ERROR_BACKUP_FILE_INCORRECT_FORMAT</span></span>           |
|  <span data-ttu-id="c2c4e-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="c2c4e-115">Message Text</span></span>   |     <span data-ttu-id="c2c4e-116">备份文件格式不正确。</span><span class="sxs-lookup"><span data-stu-id="c2c4e-116">The backup file does not have the correct format.</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="c2c4e-117">解释</span><span class="sxs-lookup"><span data-stu-id="c2c4e-117">Explanation</span></span>  
 <span data-ttu-id="c2c4e-118">备份文件格式不正确。</span><span class="sxs-lookup"><span data-stu-id="c2c4e-118">The backup file does not have the correct format.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="c2c4e-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="c2c4e-119">User Action</span></span>  
 <span data-ttu-id="c2c4e-120">检查您是否具有正确的文件和位置。</span><span class="sxs-lookup"><span data-stu-id="c2c4e-120">Check that you have the correct file and location.</span></span> <span data-ttu-id="c2c4e-121">还应确认在该文件夹中不存在具有 .BAK 扩展名的其他文件，因为 ENTSSO 系统可能会将这些文件与实际的备份文件相混淆。</span><span class="sxs-lookup"><span data-stu-id="c2c4e-121">You should also confirm that there are no other files in that folder with the .BAK extension, as the ENTSSO system may confuse them with the actual backup file.</span></span>