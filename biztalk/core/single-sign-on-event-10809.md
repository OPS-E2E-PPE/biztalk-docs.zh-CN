---
title: 单一登录：Event 10809 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7331d12b-1000-4a60-83b3-f092968e0e51
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3dc0f1b98ed1b9b3e414888b01f2693a9f1786f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65293005"
---
# <a name="single-sign-on-event-10809"></a><span data-ttu-id="d888a-102">单一登录：事件 10809</span><span class="sxs-lookup"><span data-stu-id="d888a-102">Single Sign-On: Event 10809</span></span>
## <a name="details"></a><span data-ttu-id="d888a-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d888a-103">Details</span></span>  
  
|                 |                                                                   |
|-----------------|-------------------------------------------------------------------|
|  <span data-ttu-id="d888a-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d888a-104">Product Name</span></span>   |                     <span data-ttu-id="d888a-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="d888a-105">Enterprise Single Sign-On</span></span>                     |
| <span data-ttu-id="d888a-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="d888a-106">Product Version</span></span> |    [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]     |
|    <span data-ttu-id="d888a-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d888a-107">Event ID</span></span>     |                               <span data-ttu-id="d888a-108">10809</span><span class="sxs-lookup"><span data-stu-id="d888a-108">10809</span></span>                               |
|  <span data-ttu-id="d888a-109">事件源</span><span class="sxs-lookup"><span data-stu-id="d888a-109">Event Source</span></span>   |                              <span data-ttu-id="d888a-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="d888a-110">ENTSSO</span></span>                               |
|    <span data-ttu-id="d888a-111">组件</span><span class="sxs-lookup"><span data-stu-id="d888a-111">Component</span></span>    |                                <span data-ttu-id="d888a-112">不可用</span><span class="sxs-lookup"><span data-stu-id="d888a-112">N/A</span></span>                                |
|  <span data-ttu-id="d888a-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="d888a-113">Symbolic Name</span></span>  |                  <span data-ttu-id="d888a-114">ENTSSO_E_HISSO_APP_NOT_ENABLED</span><span class="sxs-lookup"><span data-stu-id="d888a-114">ENTSSO_E_HISSO_APP_NOT_ENABLED</span></span>                   |
|  <span data-ttu-id="d888a-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="d888a-115">Message Text</span></span>   | <span data-ttu-id="d888a-116">该应用不支持为主机启动的单一登录。</span><span class="sxs-lookup"><span data-stu-id="d888a-116">The application is not enabled for Host Initiated Single Sign-On.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="d888a-117">解释</span><span class="sxs-lookup"><span data-stu-id="d888a-117">Explanation</span></span>  
 <span data-ttu-id="d888a-118">该应用不支持为主机启动的单一登录。</span><span class="sxs-lookup"><span data-stu-id="d888a-118">The application is not enabled for Host Initiated Single Sign-On.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d888a-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="d888a-119">User Action</span></span>  
 <span data-ttu-id="d888a-120">使用管理工具来配置主机启动的单一登录。</span><span class="sxs-lookup"><span data-stu-id="d888a-120">Use the administrative tools to configure Host Initiated Single Sign-On.</span></span> <span data-ttu-id="d888a-121">这会设置</span><span class="sxs-lookup"><span data-stu-id="d888a-121">This will set the</span></span>  
  
 <span data-ttu-id="d888a-122">SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS 标记应用程序。</span><span class="sxs-lookup"><span data-stu-id="d888a-122">SSO_FLAG_SSO_EXTERNAL_TO_WINDOWS flag on the application.</span></span>