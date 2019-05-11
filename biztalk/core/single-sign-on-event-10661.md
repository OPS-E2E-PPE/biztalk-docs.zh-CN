---
title: 单一登录：Event 10661 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c3418f37-770d-4021-9341-5dbe99689da6
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7aa13b06dfcf0d57c90271cd924b804717ca2f2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397583"
---
# <a name="single-sign-on-event-10661"></a><span data-ttu-id="b6fe2-102">单一登录：事件 10661</span><span class="sxs-lookup"><span data-stu-id="b6fe2-102">Single Sign-On: Event 10661</span></span>
## <a name="details"></a><span data-ttu-id="b6fe2-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="b6fe2-103">Details</span></span>  

|                 |                                                                                     |
|-----------------|-------------------------------------------------------------------------------------|
|  <span data-ttu-id="b6fe2-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="b6fe2-104">Product Name</span></span>   |                              <span data-ttu-id="b6fe2-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="b6fe2-105">Enterprise Single Sign-On</span></span>                              |
| <span data-ttu-id="b6fe2-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="b6fe2-106">Product Version</span></span> |             [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]              |
|    <span data-ttu-id="b6fe2-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="b6fe2-107">Event ID</span></span>     |                                        <span data-ttu-id="b6fe2-108">10661</span><span class="sxs-lookup"><span data-stu-id="b6fe2-108">10661</span></span>                                        |
|  <span data-ttu-id="b6fe2-109">事件源</span><span class="sxs-lookup"><span data-stu-id="b6fe2-109">Event Source</span></span>   |                                       <span data-ttu-id="b6fe2-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="b6fe2-110">ENTSSO</span></span>                                        |
|    <span data-ttu-id="b6fe2-111">组件</span><span class="sxs-lookup"><span data-stu-id="b6fe2-111">Component</span></span>    |                                         <span data-ttu-id="b6fe2-112">N\A</span><span class="sxs-lookup"><span data-stu-id="b6fe2-112">N\A</span></span>                                         |
|  <span data-ttu-id="b6fe2-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="b6fe2-113">Symbolic Name</span></span>  |                    <span data-ttu-id="b6fe2-114">SSO_ERROR_PASSWORD_SYNC_WINDOWS_START_FAILED</span><span class="sxs-lookup"><span data-stu-id="b6fe2-114">SSO_ERROR_PASSWORD_SYNC_WINDOWS_START_FAILED</span></span>                     |
|  <span data-ttu-id="b6fe2-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="b6fe2-115">Message Text</span></span>   | <span data-ttu-id="b6fe2-116">Windows （从 PCNS) 的密码同步无法 start.%r</span><span class="sxs-lookup"><span data-stu-id="b6fe2-116">Password sync for Windows (from PCNS) failed to start.%r</span></span><br /><br /> <span data-ttu-id="b6fe2-117">错误代码： %1</span><span class="sxs-lookup"><span data-stu-id="b6fe2-117">Error Code: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="b6fe2-118">解释</span><span class="sxs-lookup"><span data-stu-id="b6fe2-118">Explanation</span></span>  
 <span data-ttu-id="b6fe2-119">此错误事件表示无法启动的 Windows 密码同步。</span><span class="sxs-lookup"><span data-stu-id="b6fe2-119">This Error event indicates that password sync for Windows failed to start.</span></span>  

## <a name="user-action"></a><span data-ttu-id="b6fe2-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="b6fe2-120">User Action</span></span>  
 <span data-ttu-id="b6fe2-121">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="b6fe2-121">To resolve this error, do one or more of the following:</span></span>  

-   <span data-ttu-id="b6fe2-122">检查应用程序和系统事件日志中的关联事件。</span><span class="sxs-lookup"><span data-stu-id="b6fe2-122">Check the application and system event logs for associated events.</span></span>  

-   <span data-ttu-id="b6fe2-123">验证适配器配置属性。</span><span class="sxs-lookup"><span data-stu-id="b6fe2-123">Verify adapter configuration properties.</span></span>  

## <a name="more-info"></a><span data-ttu-id="b6fe2-124">详细信息</span><span class="sxs-lookup"><span data-stu-id="b6fe2-124">More info</span></span>

- [<span data-ttu-id="b6fe2-125">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="b6fe2-125">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)  

- <span data-ttu-id="b6fe2-126">**企业单一登录的用户界面帮助** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="b6fe2-126">**Enterprise Single Sign-On UI Help** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
