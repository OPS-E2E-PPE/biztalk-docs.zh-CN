---
title: 在导入管理包之前 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e3c13dd-613a-4885-a5d2-ad3ee492ff25
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1c11849c379a4654bed78a8e86ba263e6da428c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22299445"
---
# <a name="before-you-import-the-management-pack"></a><span data-ttu-id="4920a-102">导入管理包之前</span><span class="sxs-lookup"><span data-stu-id="4920a-102">Before You Import the Management Pack</span></span>
<span data-ttu-id="4920a-103">作为最佳做法，应将用于正在使用的操作系统的 Windows Server 管理包导入。</span><span class="sxs-lookup"><span data-stu-id="4920a-103">As a best practice, you should import the Windows Server Management Pack for the operating system that you are using.</span></span> <span data-ttu-id="4920a-104">在导入之前[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理包中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4920a-104">Before you import the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Management Pack, take the following actions:</span></span>  
  
-   <span data-ttu-id="4920a-105">确保安装了 Operations Manager 2007 R2/2012年。</span><span class="sxs-lookup"><span data-stu-id="4920a-105">Ensure that Operations Manager 2007 R2/2012 is installed.</span></span>  
  
-   <span data-ttu-id="4920a-106">你必须是 SCOM 管理员组或 SCOM 作者组的成员。</span><span class="sxs-lookup"><span data-stu-id="4920a-106">You must be a member of either the SCOM Administrators group or the SCOM Authors group.</span></span> <span data-ttu-id="4920a-107">SCOM 管理服务器上的本地管理员具有所有权限和授予的 SCOM 管理员组的权限。</span><span class="sxs-lookup"><span data-stu-id="4920a-107">Local administrators on the SCOM Management Server have all the rights and permissions that are granted to the SCOM Administrators group.</span></span>  
  
-   <span data-ttu-id="4920a-108">通过将设置你的 BizTalk 服务器为 Operations Manager 中被管理的计算机部署上每个你想要管理的 BizTalk Server 的 SCOM 代理。</span><span class="sxs-lookup"><span data-stu-id="4920a-108">Set up your BizTalk Servers as managed computers in Operations Manager by deploying the SCOM agents on each BizTalk Server that you want to manage.</span></span> <span data-ttu-id="4920a-109">SCOM 代理部署涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="4920a-109">The SCOM agent deployment involves the following tasks:</span></span>  
  
    -   <span data-ttu-id="4920a-110">安装 SCOM 代理。</span><span class="sxs-lookup"><span data-stu-id="4920a-110">Install the SCOM agent.</span></span>  
  
    -   <span data-ttu-id="4920a-111">创建 BizTalk SCOM 代理帐户。</span><span class="sxs-lookup"><span data-stu-id="4920a-111">Create a BizTalk SCOM agent account.</span></span>  
  
    -   <span data-ttu-id="4920a-112">配置**运行方式**帐户。</span><span class="sxs-lookup"><span data-stu-id="4920a-112">Configure a **Run As** account.</span></span> <span data-ttu-id="4920a-113">将运行方式帐户添加到以下组：</span><span class="sxs-lookup"><span data-stu-id="4920a-113">Add the Run As account to the following groups:</span></span>  
  
        -   <span data-ttu-id="4920a-114">BizTalk 组。</span><span class="sxs-lookup"><span data-stu-id="4920a-114">BizTalk Groups.</span></span>  
  
        -   <span data-ttu-id="4920a-115">BizTalk 管理员。</span><span class="sxs-lookup"><span data-stu-id="4920a-115">BizTalk Administrators.</span></span>  
  
        -   <span data-ttu-id="4920a-116">SSO 管理员。</span><span class="sxs-lookup"><span data-stu-id="4920a-116">SSO Administrators.</span></span>  
  
        -   <span data-ttu-id="4920a-117">SSO Affiliate 管理员。</span><span class="sxs-lookup"><span data-stu-id="4920a-117">SSO Affiliate Administrators.</span></span>  
  
    -   <span data-ttu-id="4920a-118">秨 ﹍ 菏跌。</span><span class="sxs-lookup"><span data-stu-id="4920a-118">Initiate monitoring.</span></span>  
  
-   <span data-ttu-id="4920a-119">在 Operation Manager 控制台中，被管理的计算机处于正常状态。</span><span class="sxs-lookup"><span data-stu-id="4920a-119">In Operation Manager Console, managed computers are in a healthy state.</span></span>  
  
-   <span data-ttu-id="4920a-120">配置需要设置，如任何所需的运行方式帐户或配置文件的任何用户帐户。</span><span class="sxs-lookup"><span data-stu-id="4920a-120">Configure any user accounts that have to be set up, such as any required Run As accounts or profiles.</span></span> <span data-ttu-id="4920a-121">此管理包包括运行方式配置文件命名为"BizTalk Server 监视帐户"和"BizTalk Server 发现帐户"上的每个代理基础定义具体的凭据。</span><span class="sxs-lookup"><span data-stu-id="4920a-121">This management pack includes Run As profiles named “BizTalk Server Monitoring Account” and “BizTalk Server Discovery Account” to define specific credentials on a per-agent basis.</span></span> <span data-ttu-id="4920a-122">你可能需要在导入管理包之后，为一些代理使用此运行方式配置文件。</span><span class="sxs-lookup"><span data-stu-id="4920a-122">You may have to use this Run As profile for some agents after you import the management pack.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4920a-123">在本节中</span><span class="sxs-lookup"><span data-stu-id="4920a-123">In this section</span></span>  
  
-   [<span data-ttu-id="4920a-124">此管理包中的文件</span><span class="sxs-lookup"><span data-stu-id="4920a-124">Files in This Management Pack</span></span>](../technical-guides/files-in-this-management-pack.md)  
  
-   [<span data-ttu-id="4920a-125">推荐的其他管理包</span><span class="sxs-lookup"><span data-stu-id="4920a-125">Recommended Additional Management Packs</span></span>](../technical-guides/recommended-additional-management-packs.md)