---
title: 单一登录： 事件 10589 |Microsoft 文档
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
ms.openlocfilehash: 56bb848711a627ceaea70085d770db7b0c759e9a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271573"
---
# <a name="single-sign-on-event-10589"></a><span data-ttu-id="07a18-102">单一登录： 事件 10589</span><span class="sxs-lookup"><span data-stu-id="07a18-102">Single Sign-On: Event 10589</span></span>
## <a name="details"></a><span data-ttu-id="07a18-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="07a18-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="07a18-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="07a18-104">Product Name</span></span>|<span data-ttu-id="07a18-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="07a18-105">Enterprise Single Sign-On</span></span>|  
|<span data-ttu-id="07a18-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="07a18-106">Product Version</span></span>|[!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]|  
|<span data-ttu-id="07a18-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="07a18-107">Event ID</span></span>|<span data-ttu-id="07a18-108">10589</span><span class="sxs-lookup"><span data-stu-id="07a18-108">10589</span></span>|  
|<span data-ttu-id="07a18-109">事件源</span><span class="sxs-lookup"><span data-stu-id="07a18-109">Event Source</span></span>|<span data-ttu-id="07a18-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="07a18-110">ENTSSO</span></span>|  
|<span data-ttu-id="07a18-111">组件</span><span class="sxs-lookup"><span data-stu-id="07a18-111">Component</span></span>|<span data-ttu-id="07a18-112">N/A</span><span class="sxs-lookup"><span data-stu-id="07a18-112">N/A</span></span>|  
|<span data-ttu-id="07a18-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="07a18-113">Symbolic Name</span></span>|<span data-ttu-id="07a18-114">SSO_ERROR_BACKUP_SECRET_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="07a18-114">SSO_ERROR_BACKUP_SECRET_REQUIRED</span></span>|  
|<span data-ttu-id="07a18-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="07a18-115">Message Text</span></span>|<span data-ttu-id="07a18-116">尚未备份主密钥。</span><span class="sxs-lookup"><span data-stu-id="07a18-116">The master secret has not been backed up.</span></span> <span data-ttu-id="07a18-117">如果丢失主密钥，则存储在 SSO 系统中的所有信息会永久丢失，并且您的系统也无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="07a18-117">If you lose the master secret all the information stored in the SSO system will be lost permanently and your systems may fail to work correctly.</span></span> <span data-ttu-id="07a18-118">请使用 SSO 管理工具来备份主密钥。</span><span class="sxs-lookup"><span data-stu-id="07a18-118">Please use the SSO administration tools to back up your master secret.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="07a18-119">解释</span><span class="sxs-lookup"><span data-stu-id="07a18-119">Explanation</span></span>  
 <span data-ttu-id="07a18-120">尚未备份主密钥。</span><span class="sxs-lookup"><span data-stu-id="07a18-120">The master secret has not been backed up.</span></span> <span data-ttu-id="07a18-121">如果丢失主密钥，则存储在 SSO 系统中的所有信息会永久丢失，并且您的系统也无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="07a18-121">If you lose the master secret all the information stored in the SSO system will be lost permanently and your systems may fail to work correctly.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="07a18-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="07a18-122">User Action</span></span>  
 <span data-ttu-id="07a18-123">有关备份主密钥的信息，请参阅[管理主密钥](../core/managing-the-master-secret.md)。</span><span class="sxs-lookup"><span data-stu-id="07a18-123">For information on backing up the master secret, see [Managing the Master Secret](../core/managing-the-master-secret.md).</span></span>