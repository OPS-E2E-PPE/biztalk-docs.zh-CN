---
title: 单一登录： 事件 10658 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5bee12d-502b-4fee-bc84-25807eb0e48e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: dd6ea4cb33e6df4fe8a59fc1041861bdb530aaa4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982246"
---
# <a name="single-sign-on-event-10658"></a><span data-ttu-id="35b15-102">单一登录： 事件 10658</span><span class="sxs-lookup"><span data-stu-id="35b15-102">Single Sign-On: Event 10658</span></span>
## <a name="details"></a><span data-ttu-id="35b15-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="35b15-103">Details</span></span>  

|                 |                                                                                   |
|-----------------|-----------------------------------------------------------------------------------|
|  <span data-ttu-id="35b15-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="35b15-104">Product Name</span></span>   |                             <span data-ttu-id="35b15-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="35b15-105">Enterprise Single Sign-On</span></span>                             |
| <span data-ttu-id="35b15-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="35b15-106">Product Version</span></span> |            [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]             |
|    <span data-ttu-id="35b15-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="35b15-107">Event ID</span></span>     |                                       <span data-ttu-id="35b15-108">10658</span><span class="sxs-lookup"><span data-stu-id="35b15-108">10658</span></span>                                       |
|  <span data-ttu-id="35b15-109">事件源</span><span class="sxs-lookup"><span data-stu-id="35b15-109">Event Source</span></span>   |                                      <span data-ttu-id="35b15-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="35b15-110">ENTSSO</span></span>                                       |
|    <span data-ttu-id="35b15-111">组件</span><span class="sxs-lookup"><span data-stu-id="35b15-111">Component</span></span>    |                                        <span data-ttu-id="35b15-112">N\A</span><span class="sxs-lookup"><span data-stu-id="35b15-112">N\A</span></span>                                        |
|  <span data-ttu-id="35b15-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="35b15-113">Symbolic Name</span></span>  |                   <span data-ttu-id="35b15-114">SSO_ERROR_PASSWORD_SYNC_ADAPTERS_START_FAILED</span><span class="sxs-lookup"><span data-stu-id="35b15-114">SSO_ERROR_PASSWORD_SYNC_ADAPTERS_START_FAILED</span></span>                   |
|  <span data-ttu-id="35b15-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="35b15-115">Message Text</span></span>   | <span data-ttu-id="35b15-116">外部适配器的密码同步启动失败。%r</span><span class="sxs-lookup"><span data-stu-id="35b15-116">Password sync for external adapters failed to start.%r</span></span><br /><br /> <span data-ttu-id="35b15-117">错误代码： %1</span><span class="sxs-lookup"><span data-stu-id="35b15-117">Error Code: %1</span></span> |

## <a name="explanation"></a><span data-ttu-id="35b15-118">解释</span><span class="sxs-lookup"><span data-stu-id="35b15-118">Explanation</span></span>  
 <span data-ttu-id="35b15-119">此错误事件表示，无法启动外部适配器的密码同步。</span><span class="sxs-lookup"><span data-stu-id="35b15-119">This Error event indicates that password sync for external adapters failed to start.</span></span>  

## <a name="user-action"></a><span data-ttu-id="35b15-120">用户操作</span><span class="sxs-lookup"><span data-stu-id="35b15-120">User Action</span></span>  
 <span data-ttu-id="35b15-121">若要解决此错误，请执行下列一项或多项操作:</span><span class="sxs-lookup"><span data-stu-id="35b15-121">To resolve this error, do one or more of the following:</span></span>  

-   <span data-ttu-id="35b15-122">检查相关事件的应用程序和系统事件日志。</span><span class="sxs-lookup"><span data-stu-id="35b15-122">Check the application and system event logs for associated events.</span></span>  

-   <span data-ttu-id="35b15-123">验证适配器配置属性。</span><span class="sxs-lookup"><span data-stu-id="35b15-123">Verify adapter configuration properties.</span></span>  

## <a name="more-info"></a><span data-ttu-id="35b15-124">详细信息</span><span class="sxs-lookup"><span data-stu-id="35b15-124">More info</span></span>  

- [<span data-ttu-id="35b15-125">如何管理密码同步</span><span class="sxs-lookup"><span data-stu-id="35b15-125">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)  

- <span data-ttu-id="35b15-126">**企业单一登录的用户界面帮助** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="35b15-126">**Enterprise Single Sign-On UI Help** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
