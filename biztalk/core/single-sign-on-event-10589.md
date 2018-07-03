---
title: 单一登录： 事件 10589 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0fe962bb-e9bb-4107-a5fb-21c180d54e21
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b1f8dd6c8a6045f9e4e1678aa06faec8bb783c1a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36986182"
---
# <a name="single-sign-on-event-10589"></a><span data-ttu-id="898ea-102">单一登录： 事件 10589</span><span class="sxs-lookup"><span data-stu-id="898ea-102">Single Sign-On: Event 10589</span></span>
## <a name="details"></a><span data-ttu-id="898ea-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="898ea-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                                                                                   |
|-----------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="898ea-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="898ea-104">Product Name</span></span>   |                                                                                                                     <span data-ttu-id="898ea-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="898ea-105">Enterprise Single Sign-On</span></span>                                                                                                                     |
| <span data-ttu-id="898ea-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="898ea-106">Product Version</span></span> |                                                                                                    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                                                     |
|    <span data-ttu-id="898ea-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="898ea-107">Event ID</span></span>     |                                                                                                                               <span data-ttu-id="898ea-108">10589</span><span class="sxs-lookup"><span data-stu-id="898ea-108">10589</span></span>                                                                                                                               |
|  <span data-ttu-id="898ea-109">事件源</span><span class="sxs-lookup"><span data-stu-id="898ea-109">Event Source</span></span>   |                                                                                                                              <span data-ttu-id="898ea-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="898ea-110">ENTSSO</span></span>                                                                                                                               |
|    <span data-ttu-id="898ea-111">组件</span><span class="sxs-lookup"><span data-stu-id="898ea-111">Component</span></span>    |                                                                                                                                <span data-ttu-id="898ea-112">N/A</span><span class="sxs-lookup"><span data-stu-id="898ea-112">N/A</span></span>                                                                                                                                |
|  <span data-ttu-id="898ea-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="898ea-113">Symbolic Name</span></span>  |                                                                                                                 <span data-ttu-id="898ea-114">SSO_ERROR_BACKUP_SECRET_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="898ea-114">SSO_ERROR_BACKUP_SECRET_REQUIRED</span></span>                                                                                                                  |
|  <span data-ttu-id="898ea-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="898ea-115">Message Text</span></span>   | <span data-ttu-id="898ea-116">尚未备份主密钥。</span><span class="sxs-lookup"><span data-stu-id="898ea-116">The master secret has not been backed up.</span></span> <span data-ttu-id="898ea-117">如果丢失主密钥，则存储在 SSO 系统中的所有信息会永久丢失，并且您的系统也无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="898ea-117">If you lose the master secret all the information stored in the SSO system will be lost permanently and your systems may fail to work correctly.</span></span> <span data-ttu-id="898ea-118">请使用 SSO 管理工具来备份主密钥。</span><span class="sxs-lookup"><span data-stu-id="898ea-118">Please use the SSO administration tools to back up your master secret.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="898ea-119">解释</span><span class="sxs-lookup"><span data-stu-id="898ea-119">Explanation</span></span>  
 <span data-ttu-id="898ea-120">尚未备份主密钥。</span><span class="sxs-lookup"><span data-stu-id="898ea-120">The master secret has not been backed up.</span></span> <span data-ttu-id="898ea-121">如果丢失主密钥，则存储在 SSO 系统中的所有信息会永久丢失，并且您的系统也无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="898ea-121">If you lose the master secret all the information stored in the SSO system will be lost permanently and your systems may fail to work correctly.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="898ea-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="898ea-122">User Action</span></span>  
 <span data-ttu-id="898ea-123">有关备份主密钥的信息，请参阅[管理主密钥](../core/managing-the-master-secret.md)。</span><span class="sxs-lookup"><span data-stu-id="898ea-123">For information on backing up the master secret, see [Managing the Master Secret](../core/managing-the-master-secret.md).</span></span>