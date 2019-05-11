---
title: 单一登录：事件 10564 |Microsoft Docs
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
ms.openlocfilehash: 9ddea5def52677643930d215bd17a82359b55d90
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398801"
---
# <a name="single-sign-on-event-10564"></a><span data-ttu-id="32014-102">单一登录：事件 10564</span><span class="sxs-lookup"><span data-stu-id="32014-102">Single Sign-On: Event 10564</span></span>
## <a name="details"></a><span data-ttu-id="32014-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="32014-103">Details</span></span>  
  
|                 |                                                            |
|-----------------|------------------------------------------------------------|
|  <span data-ttu-id="32014-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="32014-104">Product Name</span></span>   |                 <span data-ttu-id="32014-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="32014-105">Enterprise Single Sign-On</span></span>                  |
| <span data-ttu-id="32014-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="32014-106">Product Version</span></span> | [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)] |
|    <span data-ttu-id="32014-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="32014-107">Event ID</span></span>     |                           <span data-ttu-id="32014-108">10564</span><span class="sxs-lookup"><span data-stu-id="32014-108">10564</span></span>                            |
|  <span data-ttu-id="32014-109">事件源</span><span class="sxs-lookup"><span data-stu-id="32014-109">Event Source</span></span>   |                           <span data-ttu-id="32014-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="32014-110">ENTSSO</span></span>                           |
|    <span data-ttu-id="32014-111">组件</span><span class="sxs-lookup"><span data-stu-id="32014-111">Component</span></span>    |                            <span data-ttu-id="32014-112">不可用</span><span class="sxs-lookup"><span data-stu-id="32014-112">N/A</span></span>                             |
|  <span data-ttu-id="32014-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="32014-113">Symbolic Name</span></span>  |           <span data-ttu-id="32014-114">SSO_ERROR_BACKUP_FILE_INCORRECT_FORMAT</span><span class="sxs-lookup"><span data-stu-id="32014-114">SSO_ERROR_BACKUP_FILE_INCORRECT_FORMAT</span></span>           |
|  <span data-ttu-id="32014-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="32014-115">Message Text</span></span>   |     <span data-ttu-id="32014-116">备份文件没有正确的格式。</span><span class="sxs-lookup"><span data-stu-id="32014-116">The backup file does not have the correct format.</span></span>      |
  
## <a name="explanation"></a><span data-ttu-id="32014-117">解释</span><span class="sxs-lookup"><span data-stu-id="32014-117">Explanation</span></span>  
 <span data-ttu-id="32014-118">备份文件没有正确的格式。</span><span class="sxs-lookup"><span data-stu-id="32014-118">The backup file does not have the correct format.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="32014-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="32014-119">User Action</span></span>  
 <span data-ttu-id="32014-120">检查你具有正确的文件和位置。</span><span class="sxs-lookup"><span data-stu-id="32014-120">Check that you have the correct file and location.</span></span> <span data-ttu-id="32014-121">此外应确认在该文件夹中没有任何其他文件。BAK 扩展作为 ENTSSO 系统可能会想让他们使用实际的备份文件。</span><span class="sxs-lookup"><span data-stu-id="32014-121">You should also confirm that there are no other files in that folder with the .BAK extension, as the ENTSSO system may confuse them with the actual backup file.</span></span>