---
title: 单一登录：事件 10565 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6d279491-dc0d-44c4-a77e-a67498a3481d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dea7d2284d12bacd1fa4bb08bc5870594891e4e7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398793"
---
# <a name="single-sign-on-event-10565"></a><span data-ttu-id="a4c43-102">单一登录：事件 10565</span><span class="sxs-lookup"><span data-stu-id="a4c43-102">Single Sign-On: Event 10565</span></span>
## <a name="details"></a><span data-ttu-id="a4c43-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a4c43-103">Details</span></span>  
  
|                 |                                                                                                                                                                                                               |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="a4c43-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a4c43-104">Product Name</span></span>   |                                                                                           <span data-ttu-id="a4c43-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="a4c43-105">Enterprise Single Sign-On</span></span>                                                                                           |
| <span data-ttu-id="a4c43-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="a4c43-106">Product Version</span></span> |                                                                          [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                                                           |
|    <span data-ttu-id="a4c43-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a4c43-107">Event ID</span></span>     |                                                                                                     <span data-ttu-id="a4c43-108">10565</span><span class="sxs-lookup"><span data-stu-id="a4c43-108">10565</span></span>                                                                                                     |
|  <span data-ttu-id="a4c43-109">事件源</span><span class="sxs-lookup"><span data-stu-id="a4c43-109">Event Source</span></span>   |                                                                                                    <span data-ttu-id="a4c43-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="a4c43-110">ENTSSO</span></span>                                                                                                     |
|    <span data-ttu-id="a4c43-111">组件</span><span class="sxs-lookup"><span data-stu-id="a4c43-111">Component</span></span>    |                                                                                                      <span data-ttu-id="a4c43-112">不可用</span><span class="sxs-lookup"><span data-stu-id="a4c43-112">N/A</span></span>                                                                                                      |
|  <span data-ttu-id="a4c43-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="a4c43-113">Symbolic Name</span></span>  |                                                                                       <span data-ttu-id="a4c43-114">SSO_ERROR_SECRET_VALIDATE_FAILED</span><span class="sxs-lookup"><span data-stu-id="a4c43-114">SSO_ERROR_SECRET_VALIDATE_FAILED</span></span>                                                                                        |
|  <span data-ttu-id="a4c43-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="a4c43-115">Message Text</span></span>   | <span data-ttu-id="a4c43-116">无法从注册表加载密钥。</span><span class="sxs-lookup"><span data-stu-id="a4c43-116">The secret could not be loaded from the registry.</span></span> <span data-ttu-id="a4c43-117">SSO 服务的服务帐户可能已更改，或者密钥可能已损坏。</span><span class="sxs-lookup"><span data-stu-id="a4c43-117">The service account for the SSO service may have been changed or the secret may be corrupted.</span></span> <span data-ttu-id="a4c43-118">从备份 file.%r 还原该密钥</span><span class="sxs-lookup"><span data-stu-id="a4c43-118">Restore the secret from a backup file.%r</span></span><br /><br /> <span data-ttu-id="a4c43-119">MSID: %1</span><span class="sxs-lookup"><span data-stu-id="a4c43-119">MSID: %1</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="a4c43-120">解释</span><span class="sxs-lookup"><span data-stu-id="a4c43-120">Explanation</span></span>  
 <span data-ttu-id="a4c43-121">很可能在系统中的管理员已更改 SSO 服务帐户，因此无法解密。</span><span class="sxs-lookup"><span data-stu-id="a4c43-121">It is likely that an administrator in the system has changed the SSO Service account, making decryption impossible.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a4c43-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="a4c43-122">User Action</span></span>  
 <span data-ttu-id="a4c43-123">查找更改 SSO 服务帐户的人员，然后从备份文件还原密钥。</span><span class="sxs-lookup"><span data-stu-id="a4c43-123">Find the person who changed the SSO Service account, and then restore the secret from a backup file.</span></span> <span data-ttu-id="a4c43-124">还原密钥的详细信息，请参阅[管理主密钥](../core/managing-the-master-secret.md)。</span><span class="sxs-lookup"><span data-stu-id="a4c43-124">For more information on restoring the secret, see [Managing the Master Secret](../core/managing-the-master-secret.md).</span></span>