---
title: 单一登录：Event 10820 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2da93a2c-d00d-4ca0-a0cf-453cee4bf3c3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 59b0795514529e4e4236ebab96ceb5730171884f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395468"
---
# <a name="single-sign-on-event-10820"></a><span data-ttu-id="193ac-102">单一登录：事件 10820</span><span class="sxs-lookup"><span data-stu-id="193ac-102">Single Sign-On: Event 10820</span></span>
## <a name="details"></a><span data-ttu-id="193ac-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="193ac-103">Details</span></span>  
  
|                 |                                                                                              |
|-----------------|----------------------------------------------------------------------------------------------|
|  <span data-ttu-id="193ac-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="193ac-104">Product Name</span></span>   |                                  <span data-ttu-id="193ac-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="193ac-105">Enterprise Single Sign-On</span></span>                                   |
| <span data-ttu-id="193ac-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="193ac-106">Product Version</span></span> |                  [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                  |
|    <span data-ttu-id="193ac-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="193ac-107">Event ID</span></span>     |                                            <span data-ttu-id="193ac-108">10820</span><span class="sxs-lookup"><span data-stu-id="193ac-108">10820</span></span>                                             |
|  <span data-ttu-id="193ac-109">事件源</span><span class="sxs-lookup"><span data-stu-id="193ac-109">Event Source</span></span>   |                                            <span data-ttu-id="193ac-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="193ac-110">ENTSSO</span></span>                                            |
|    <span data-ttu-id="193ac-111">组件</span><span class="sxs-lookup"><span data-stu-id="193ac-111">Component</span></span>    |                                             <span data-ttu-id="193ac-112">不可用</span><span class="sxs-lookup"><span data-stu-id="193ac-112">N/A</span></span>                                              |
|  <span data-ttu-id="193ac-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="193ac-113">Symbolic Name</span></span>  |                                <span data-ttu-id="193ac-114">ENTSSO_E_REQUIRE_OLD_PASSWORD</span><span class="sxs-lookup"><span data-stu-id="193ac-114">ENTSSO_E_REQUIRE_OLD_PASSWORD</span></span>                                 |
|  <span data-ttu-id="193ac-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="193ac-115">Message Text</span></span>   | <span data-ttu-id="193ac-116">更改外部帐户的密码时，适配器必须提供旧密码。</span><span class="sxs-lookup"><span data-stu-id="193ac-116">When changing the password for an external account the adapter must supply the old password.</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="193ac-117">解释</span><span class="sxs-lookup"><span data-stu-id="193ac-117">Explanation</span></span>  
 <span data-ttu-id="193ac-118">此应用程序配置密码同步适配器所需提供旧密码的方式。</span><span class="sxs-lookup"><span data-stu-id="193ac-118">This application is configured in such a way that the password sync adapter is required to supply the old password.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="193ac-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="193ac-119">User Action</span></span>  
 <span data-ttu-id="193ac-120">检查您的密码同步适配器的配置。</span><span class="sxs-lookup"><span data-stu-id="193ac-120">Check the configuration of your password sync adapter.</span></span>