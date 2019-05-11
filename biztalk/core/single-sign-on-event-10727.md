---
title: 单一登录：Event 10727 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8ff7ac94-6f1e-4e56-853e-efc50b1fa1b6
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4a6dcf108030a1679601e7c7a39a0f09b13d81a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65259011"
---
# <a name="single-sign-on-event-10727"></a><span data-ttu-id="f4aa1-102">单一登录：事件 10727</span><span class="sxs-lookup"><span data-stu-id="f4aa1-102">Single Sign-On: Event 10727</span></span>
## <a name="details"></a><span data-ttu-id="f4aa1-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f4aa1-103">Details</span></span>  

|                 |                                                                                                                                          |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="f4aa1-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f4aa1-104">Product Name</span></span>   |                                                        <span data-ttu-id="f4aa1-105">企业单一登录</span><span class="sxs-lookup"><span data-stu-id="f4aa1-105">Enterprise Single Sign-On</span></span>                                                         |
| <span data-ttu-id="f4aa1-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="f4aa1-106">Product Version</span></span> |                                        [!INCLUDE[btsSSOVersion](../includes/btsssoversion-md.md)]                                        |
|    <span data-ttu-id="f4aa1-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f4aa1-107">Event ID</span></span>     |                                                                  <span data-ttu-id="f4aa1-108">10727</span><span class="sxs-lookup"><span data-stu-id="f4aa1-108">10727</span></span>                                                                   |
|  <span data-ttu-id="f4aa1-109">事件源</span><span class="sxs-lookup"><span data-stu-id="f4aa1-109">Event Source</span></span>   |                                                                  <span data-ttu-id="f4aa1-110">ENTSSO</span><span class="sxs-lookup"><span data-stu-id="f4aa1-110">ENTSSO</span></span>                                                                  |
|    <span data-ttu-id="f4aa1-111">组件</span><span class="sxs-lookup"><span data-stu-id="f4aa1-111">Component</span></span>    |                                                                   <span data-ttu-id="f4aa1-112">N\A</span><span class="sxs-lookup"><span data-stu-id="f4aa1-112">N\A</span></span>                                                                    |
|  <span data-ttu-id="f4aa1-113">符号名称</span><span class="sxs-lookup"><span data-stu-id="f4aa1-113">Symbolic Name</span></span>  |                                                      <span data-ttu-id="f4aa1-114">SSO_WARN_REPLAY_RECORD_FAILED</span><span class="sxs-lookup"><span data-stu-id="f4aa1-114">SSO_WARN_REPLAY_RECORD_FAILED</span></span>                                                       |
|  <span data-ttu-id="f4aa1-115">消息正文</span><span class="sxs-lookup"><span data-stu-id="f4aa1-115">Message Text</span></span>   | <span data-ttu-id="f4aa1-116">重播存储的外部密码更改 failed.%r</span><span class="sxs-lookup"><span data-stu-id="f4aa1-116">Replay of the stored external password change failed.%r</span></span><br /><br /> <span data-ttu-id="f4aa1-117">适配器: %1 %r</span><span class="sxs-lookup"><span data-stu-id="f4aa1-117">Adapter: %1%r</span></span><br /><br /> <span data-ttu-id="f4aa1-118">文件名称: %2 %r</span><span class="sxs-lookup"><span data-stu-id="f4aa1-118">File Name: %2%r</span></span><br /><br /> <span data-ttu-id="f4aa1-119">错误代码： %3</span><span class="sxs-lookup"><span data-stu-id="f4aa1-119">Error Code: %3</span></span> |

## <a name="explanation"></a><span data-ttu-id="f4aa1-120">解释</span><span class="sxs-lookup"><span data-stu-id="f4aa1-120">Explanation</span></span>  
 <span data-ttu-id="f4aa1-121">此警告表明，SSO 无法重播在重播文件中记录的密码更改。</span><span class="sxs-lookup"><span data-stu-id="f4aa1-121">This Warning indicates that SSO was unable to replay a password change recorded in the replay file.</span></span>  

 <span data-ttu-id="f4aa1-122">ENTSSO 服务器无法与 SSO 数据库取得联系时，密码同步使用重播文件。</span><span class="sxs-lookup"><span data-stu-id="f4aa1-122">Replay files are used by password sync when the ENTSSO server cannot contact the SSO database.</span></span> <span data-ttu-id="f4aa1-123">进度文件指示，距离通过 SSO 无法重播文件中用例联系人与 SSO 数据库会再次读取。</span><span class="sxs-lookup"><span data-stu-id="f4aa1-123">A progress file indicates how far through SSO was able to read the replay file in-case contact with the SSO database is again lost.</span></span>  

## <a name="user-action"></a><span data-ttu-id="f4aa1-124">用户操作</span><span class="sxs-lookup"><span data-stu-id="f4aa1-124">User Action</span></span>  
 <span data-ttu-id="f4aa1-125">若要解决此警告，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f4aa1-125">To resolve this warning, do the following:</span></span>  

- <span data-ttu-id="f4aa1-126">检查有相关事件的系统和应用程序事件日志。</span><span class="sxs-lookup"><span data-stu-id="f4aa1-126">Check System and Application event logs for associated events.</span></span>  

  <span data-ttu-id="f4aa1-127">有关详细信息，请参阅下列资源：</span><span class="sxs-lookup"><span data-stu-id="f4aa1-127">For more information, see the following resources:</span></span>  

- [<span data-ttu-id="f4aa1-128">如何配置密码同步</span><span class="sxs-lookup"><span data-stu-id="f4aa1-128">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  

- [<span data-ttu-id="f4aa1-129">密码同步</span><span class="sxs-lookup"><span data-stu-id="f4aa1-129">Password Synchronization</span></span>](../core/password-synchronization2.md)
