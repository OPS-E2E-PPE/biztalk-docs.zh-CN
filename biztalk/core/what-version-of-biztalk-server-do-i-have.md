---
title: 我的 BizTalk Server 是哪个版本？ | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cb651202-f682-4e5f-8a79-221877af20a7
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7003f2d3c61345462ca484f627110a6e507e748
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976974"
---
# <a name="what-version-of-biztalk-server-do-i-have"></a><span data-ttu-id="110fa-103">我的 BizTalk Server 是哪个版本？</span><span class="sxs-lookup"><span data-stu-id="110fa-103">What Version of BizTalk Server Do I Have?</span></span>
<span data-ttu-id="110fa-104">您可能会运行不同版本和不同版本的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="110fa-104">You may be running different versions and different editions of [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span> <span data-ttu-id="110fa-105">本主题演示如何确定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]安装信息，包括版本数、 版本和安装路径。</span><span class="sxs-lookup"><span data-stu-id="110fa-105">This topic shows you how to determine [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation information, including the version number, edition, and installation path.</span></span>  

## <a name="use-the-registry"></a><span data-ttu-id="110fa-106">使用注册表</span><span class="sxs-lookup"><span data-stu-id="110fa-106">Use the registry</span></span>

1. <span data-ttu-id="110fa-107">选择**启动**，类型`regedt32`，然后打开它。</span><span class="sxs-lookup"><span data-stu-id="110fa-107">Select **Start**, type `regedt32`, and then open it.</span></span>  

2. <span data-ttu-id="110fa-108">展开**HKEY_LOCAL_MACHINE**，展开**软件**，展开**Microsoft**，展开**BizTalk Server**，然后选择**3.0**。</span><span class="sxs-lookup"><span data-stu-id="110fa-108">Expand **HKEY_LOCAL_MACHINE**, expand **SOFTWARE**, expand **Microsoft**, expand **BizTalk Server**, and then select **3.0**.</span></span>  

3. <span data-ttu-id="110fa-109">右窗格中显示了安装信息，包括：</span><span class="sxs-lookup"><span data-stu-id="110fa-109">The right pane displays installation information, including:</span></span>  


   |      <span data-ttu-id="110fa-110">子项</span><span class="sxs-lookup"><span data-stu-id="110fa-110">Sub-key</span></span>       |                                                                                                         <span data-ttu-id="110fa-111">Description</span><span class="sxs-lookup"><span data-stu-id="110fa-111">Description</span></span>                                                                                                          |
   |--------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |  <span data-ttu-id="110fa-112">**InstallPath**</span><span class="sxs-lookup"><span data-stu-id="110fa-112">**InstallPath**</span></span>   |                                             <span data-ttu-id="110fa-113">列出你安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的安装路径。</span><span class="sxs-lookup"><span data-stu-id="110fa-113">Lists the installation path where you installed [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].</span></span>                                              |
   | <span data-ttu-id="110fa-114">**ProductEdition**</span><span class="sxs-lookup"><span data-stu-id="110fa-114">**ProductEdition**</span></span> |                                                        <span data-ttu-id="110fa-115">列出版本，包括：</span><span class="sxs-lookup"><span data-stu-id="110fa-115">Lists the edition, including:</span></span><br /><br /> <span data-ttu-id="110fa-116">-开发人员</span><span class="sxs-lookup"><span data-stu-id="110fa-116">-   Developer</span></span><br /><span data-ttu-id="110fa-117">分支</span><span class="sxs-lookup"><span data-stu-id="110fa-117">-   Branch</span></span><br /><span data-ttu-id="110fa-118">标准</span><span class="sxs-lookup"><span data-stu-id="110fa-118">-   Standard</span></span><br /><span data-ttu-id="110fa-119">-企业</span><span class="sxs-lookup"><span data-stu-id="110fa-119">-   Enterprise</span></span>                                                         |
   | <span data-ttu-id="110fa-120">ProductVersion</span><span class="sxs-lookup"><span data-stu-id="110fa-120">**ProductVersion**</span></span> | <span data-ttu-id="110fa-121">列出基本产品版本。</span><span class="sxs-lookup"><span data-stu-id="110fa-121">Lists the base product version.</span></span> <span data-ttu-id="110fa-122">有关特定产品版本，包括 service pack 和累积更新，请参阅[的 BizTalk 版本](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx)。</span><span class="sxs-lookup"><span data-stu-id="110fa-122">For specific product version, including service packs and cumulative updates, see [BizTalk Versions](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx).</span></span> |

## <a name="use-the-control-panel"></a><span data-ttu-id="110fa-123">使用控制面板</span><span class="sxs-lookup"><span data-stu-id="110fa-123">Use the control panel</span></span>

1.  <span data-ttu-id="110fa-124">选择**启动**，类型`Programs and Features`，然后打开它。</span><span class="sxs-lookup"><span data-stu-id="110fa-124">Select **Start**, type `Programs and Features`, and then open it.</span></span>  

2. <span data-ttu-id="110fa-125">在列表中，选择**Microsoft BizTalk Server**。</span><span class="sxs-lookup"><span data-stu-id="110fa-125">In the list, select **Microsoft BizTalk Server**.</span></span> <span data-ttu-id="110fa-126">列出的版本和版本。</span><span class="sxs-lookup"><span data-stu-id="110fa-126">The version and edition are listed.</span></span>

<span data-ttu-id="110fa-127">请参阅[的 BizTalk 版本](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx)。</span><span class="sxs-lookup"><span data-stu-id="110fa-127">See [BizTalk Versions](http://social.technet.microsoft.com/wiki/contents/articles/7915.biztalk-versions.aspx).</span></span>

## <a name="see-also"></a><span data-ttu-id="110fa-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="110fa-128">See Also</span></span>  
 [<span data-ttu-id="110fa-129">入门</span><span class="sxs-lookup"><span data-stu-id="110fa-129">Get started</span></span>](../core/getting-started-with-biztalk-server.md)